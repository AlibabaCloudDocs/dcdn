# 获取客户端真实IP {#concept_268963 .concept}

本文为您介绍了如何从源站获取客户端真实IP。

## 获取方式介绍 {#section_04u_5zf_vn5 .section}

经过加速后源站的服务器获取到的源IP地址为CDN加速设备的IP地址。如果您需要从源站获取客户端的真实IP地址，有如下两种方式：

-   Linux系统安装toa内核模块，使用方便且对应用完全透明，无需修改源站Linux服务器的应用程序即可获取真实客户端IP。
-   [Proxy Protocol](https://www.haproxy.com/blog/haproxy/proxy-protocol/)（本文简称PP），对系统内核没有要求，需要应用程序配合修改，通过解析文本字符串获取客户端IP。目前，Nginx和HAProxy已经支持。

## 安装toa模块 {#section_w24_xxt_1bv .section}

如果源站的入口系统是Linux系统，并且版本符合要求，可以通过安装toa模块的RPM包来获取用户真实IP。

|支持的Linux版本|RPM包下载|
|----------|------|
|CentOS 6.5|[CentOS 6.5 RPM](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/69329/cn_zh/1558418534623/tcp-toa-1.2.7-CentOS.6.5.x86_64.rpm)|
|CentOS 6.9|[CentOS 6.9 RPM](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/69329/cn_zh/1558418580192/tcp-toa-1.2.7-CentOS.6.9.x86_64.rpm)|
|CentOS 7.0|[CentOS 7.0 RPM](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/69329/cn_zh/1558418616318/tcp-toa-1.2.7-CentOS.7.0.x86_64.rpm)|
|CentOS 7.1|[CentOS 7.1 RPM](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/69329/cn_zh/1558418631669/tcp-toa-1.2.7-CentOS.7.1.x86_64.rpm)|
|CentOS 7.2|[CentOS 7.2 RPM](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/69329/cn_zh/1558418643311/tcp-toa-1.2.7-CentOS.7.2.x86_64.rpm)|
|CentOS 7.3|[CentOS 7.3 RPM](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/69329/cn_zh/1558418662202/tcp-toa-1.2.7-CentOS.7.3.x86_64.rpm)|
|CentOS 7.4|[CentOS 7.4 RPM](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/69329/cn_zh/1558418692772/tcp-toa-1.2.7-CentOS.7.4.x86_64.rpm)|
|CentOS 7.5|[CentOS 7.5 RPM](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/69329/cn_zh/1558418707824/tcp-toa-1.2.7-CentOS.7.5.x86_64.rpm)|
|alicdn.alios7|[alicdn.alios7 RPM](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/69329/cn_zh/1558418725522/tcp-toa-1.2.7-alicdn.alios7.x86_64.rpm)|

1.  通过`rpm`指令安装对应版本的包。

    ``` {#codeblock_6bd_snc_a1f}
    # rpm -ivh tcp-toa-1.2.7-alicdn.alios7.x86_64.rpm
    Preparing...                          ################################# [100%]
    Updating / installing...
       1:tcp-toa-1.2.7-alicdn.alios7      ################################# [100%]
    ```

2.  运行toa模块。

    ``` {#codeblock_ylq_knt_ypa}
    # service tcp_toa start
    [Starting tcp_toa]:
    Checking installed modules...
            tcp_toa not installed.
    Checking module files...                [OK]
    Installing tcp_toa...                   [OK]
    ```

3.  查看toa模块运行状态。

    ``` {#codeblock_jne_htj_26p}
    # lsmod | grep toa
    tcp_toa                12916  0
    ```

4.  停止toa模块。

    ``` {#codeblock_w43_wnz_c0k}
    # service tcp_toa stop
    [StoPPing tcp_toa]:
    Checking installed modules...
            tcp_toa installed.
    Checking installed tcp_toa...           [OK]
    Uninstalling tcp_toa...                 [OK]
    ```

5.  您可以通过输入`rpm -e tcp-toa` 卸载toa模块。

    ``` {#codeblock_93s_hq6_1b0}
    # rpm -e tcp-toa
    [StoPPing tcp_toa]:
    Checking installed modules...
            tcp_toa installed.
    Checking installed tcp_toa...           [OK]
    Uninstalling tcp_toa...                 [OK]
    ```


## Proxy Protcol {#section_1ax_ouc_49j .section}

PP方式获取IP需要在控制台配置进行使用，功能打开后，加速服务器和源站建立TCP连接，在传输第一个用户payload前，会传递PP协议文本。

配置Nginx接受PP，只需要将参数proxy\_protocol添加在`server`块中的`listen`指令后，详情请参见[Accepting the PROXY Protocol](Accepting%20the%20PROXY%20Protocol)。

``` {#codeblock_xwz_rkm_ygv}
http {
    #...
    server {
        listen 80   proxy_protocol;
        listen 443  ssl proxy_protocol;
        #...
    }
}
```

**说明：** 其他支持PP的应用请参见[Proxy Protcol](https://www.haproxy.com/blog/haproxy/proxy-protocol/)。

不支持PP的应用程序，需要在TCP连接建立后，读取PP的文本行并进行字符串解析来获取客户端IP，字符示例如下所示。

``` {#codeblock_x0d_t8n_0cw}
PROXY TCP4 1.1.1.2 2.2.2.2 12345 80\r\n
```

解析时先读取行直至`\n`，在按照协议进行解析，各字段定义如下。

``` {#codeblock_7zc_z4j_enn}
PROXY_STRING + single space + INET_PROTOCOL + single space + CLIENT_IP + single space + PROXY_IP + single space + CLIENT_PORT + single space + PROXY_PORT + "\r\n"
```

真实输出的PP文本行相对以上格式，在 `\r\n`之前可能还包含全局唯一的ID，用于全链路监控，如果不需要您可以忽略它。

``` {#codeblock_ll4_zv1_lvc}
"id"="xxxx"
```

