# HTTP/2设置 {#concept_tyg_c2d_zdb .concept}

## 功能介绍 {#section_vvx_d2d_zdb .section}

HTTP/2是最新的HTTP协议，已于2015年5月份正式发布。目前，Chrome、 IE11、Safari以及Firefox 等主流浏览器已经支持 HTTP/2协议。

HTTP/2优化了性能，兼容了HTTP/1.1的语义，其几大特性与SPDY相似，与HTTP/1.1有巨大区别。比如它不是文本协议而是二进制协议，而且HTTP头部采用HPACK进行压缩，支持多路复用、服务器推送等等。

HTTP/2的优势：

-   二进制协议。
-   头部压缩：HTTP/2消息头采用HPACK格式进行压缩传输，并对消息头建立索引表，相同的消息头只发送索引号，从而提高效率和速度。
-   多路复用：在HTTP/2中，不用按照次序一一对应。而且并发的多个请求或者响应中,任何一个请求的阻塞也不会影响其他的请求或者响应，这样就避免了“队头堵塞”。
-   服务器推送：在HTTP/2中服务器未经请求可以主动给客户端推送资源，大大提高了网页加载的速度。
-   安全：HTTPS将是未来的趋势，HTTP/2基于HTTPS也是未来的趋势，安全也是HTTP/2的重要特性之一。

## 操作步骤 {#section_k2c_l2d_zdb .section}

1.  在 域名管理页，选择域名，单击 **配置**。
2.  在 **HTTPS配置** \> **HTTP/2设置** 栏进行配置。
3.  打开后保存即可。![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13472/15355233844585_zh-CN.png)

    **说明：** 开启HTTP/2前，请确保HTTPS的证书已经配置成功。

    -   若您是第一次配置HTTPS证书，需等到证书配置完成并且证书生效后，才能打开HTTP/2。
    -   若您已经开启了HTTP/2，但是又关闭了HTTPS证书功能，HTTP/2会自动失效。

