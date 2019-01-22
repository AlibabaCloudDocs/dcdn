# HTTP/2 {#concept_tyg_c2d_zdb .concept}

## Introduction {#section_vvx_d2d_zdb .section}

HTTP/2, the latest HTTP protocol published in 2015, is now available in many browsers, such as Chrome, IE11, Safari, and Firefox. With main features similar to SPDY, HTTP/2 can be seen as an advanced edition of HTTP/1.1.

HTTP/2 Benefits

-   Binary protocol: Compared with HTTP 1. x, HTTP/2 segments transferring information into smaller frames and messages and encodes them by using binary, which makes the protocol more scalable. For example, data and command can be transferred by frame.
-   Content security: Based on HTTPS, HTTP/2 gives considerations to both security and performance.
-   Multiplexing: With HTTP/2, your browser can trigger multiple requests in one connection, and receive these requests in any order or at the same time. Moreover, stream dependencies is also available in multiplexing, allowing client servers to define which contents to be transferred in priority.
-   Header compression: HTTP/2 compresses and transfers message headers in the HPACK format and creates an index table for the headers. Only the index are transferred, which improves the transferring efficiency and speed.
-   Server push: Similar to SPDY, HTTP/2 allows servers to actively push contents to clients without a request, significantly improving web page loading speeds.

## Procedure {#section_k2c_l2d_zdb .section}

1.  Log on to the [DCDN console](https://dcdn.console.aliyun.com).
2.  On the Domain Names page, select a domain name and click **Configure**.

    **Note:** Make sure that you have configured HTTPS certificates before enabling HTTP/2.

    -   If it is your first time configuring HTTPS certificate, wait for a while until your configuration coming into effect.
    -   If you disable HTTPS certificates when your HTTP/2 service is running, your HTTP/2 service will be disabled automatically.
3.  Enable the HTTP/2 in **HTTPS Settings** \> **HTTP/2 Setting**.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13472/15481451834585_en-US.png)

