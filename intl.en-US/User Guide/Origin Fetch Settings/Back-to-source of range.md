# Back-to-source of range {#concept_ejr_zvw_ydb .concept}

## Introduction {#section_nzt_hww_ydb .section}

The range origin fetch feature allows a client to notify an origin site server to return partial content within a specified range. This feature accelerates delivery of large files by reducing the consumption of origin fetch traffic and improving the resource response speed.

-   To use the range origin fetch feature, an origin site must support Range requests. The origin site must be able to return correct 206 Partial Content for an HTTP request header containing a Range field.
-   When range origin fetch is enabled, a parameter request can be returned to an origin site. In this case, the origin site returns the file byte range according to the Range parameter and the CDN node returns the content in the byte range to the client.

**Note:** For example, if a request sent from a client to a CDN node contains range:0-100, the range:0-100 parameter is also contained in the request received on the origin site. When the origin site returns the parameter content to the CDN node, the node returns the content in 101 bytes ranging from 0 to 100 to the client.

-   When range origin fetch is disabled, a CDN higher-level node requests an origin site for all files. However, the requested files are not cached on the CDN node because a client automatically disconnects HTTP links after receiving bytes specified by Range. This causes a low cache hit rate and large origin fetch traffic.

**Note:** For example, if a request sent from a client to a CDN node contains range:0-100, the range:0-100 parameter isl not contained in the request received on the server. The origin site will return a complete file to the CDN node and the CDN node will return only 101 bytes to the client. However, the file cannot be cached on the CDN node because the link is disconnected.


## Note {#section_g2q_lww_ydb .section}

To use the range origin fetch feature, an origin site must support Range requests. The origin site must be able to return correct 206 Partial Content for an HTTP request header containing a Range field.

## Procedure {#section_iqc_nww_ydb .section}

1.  On the Domain Names page, select a domain name, and then click **Configure**.
2.  Go to **Origin Fetch** \> **Range Origin Fetch** to enable range origin fetch.

    ![](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/pic/68473/cn_zh/1533103680084/D5.png)


