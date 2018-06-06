# 回源Host {#concept_xpz_3sw_ydb .concept}

## 功能介绍 {#section_jvd_lsw_ydb .section}

自定义在CDN节点回源过程中所需访问的WEB服务器域名。

-   回源host是可选配置项，默认值为：
    -   如果源站是**IP**类型，回源host默认加速域名。
    -   如果源站是**OSS源站**类型，回源host默认是源站域名。
-   可选项分别是：加速域名、源站域名、自定义域名。

    **说明：** 目前不支持sni 回源。


## 操作步骤 {#section_hqx_4sw_ydb .section}

1.  在 域名管理页，选择域名，单击**配置**。
2.  在 **回源设置** \> **回源Host ** ，单击**修改配置**。
3.  选择您要加速的域名类型，单击**确定**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13456/4386_zh-CN.png)


## 源站和回源Host的区别 {#section_o4x_ysw_ydb .section}

-   源站： 源站决定了回源时，请求到的具体IP地址。

-   回源host：回源host决定回源请求访问到该IP上地址上的具体站点。


|案例|例一|例二|
|:-|:-|:-|
|源站|www.a.com|1.1.1.1|
|回源host|www.b.com|www.b.com|
|实际回源是请求到|www.a.com对应的主机上的站点 www.b.com|1.1.1.1对应的主机上的 站点www.b.comwww.b.com|

