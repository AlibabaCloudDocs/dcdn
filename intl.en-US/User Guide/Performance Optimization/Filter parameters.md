# Filter parameters {#concept_el4_c4d_zdb .concept}

## Introduction {#section_i5l_x4d_zdb .section}

When a URL request that carries a question mark \(?\) and request parameters is sent to a CDN node, the CDN node determines whether to send the request to the origin site.

-   If parameter filtering is enabled, after the request arrives at the CDN node, the URL without parameters is intercepted and requested against the origin site. Additionally, the CDN node retains only one copy.
-   If parameter filtering is disabled, different copies are cached on the CDN node for different URLs.

Recommendations

-   An HTTP request typically contains the parameters. If the content of a parameter has low priority and the parameter overview file can be ignored, we recommend that you enable the parameter filtering. This improves the file cache hit rate and the delivery efficiency.
-   If a parameter carries important information, for example, the file version information, we recommend that you set it as a reserved parameter. The system supports multiple reserved parameters. If the request contains any reserved parameters, the reserved parameters are included in the request to the origin site and are not ignored.

Usage example

For example: `http://www.abc.com/a.jpg?x=1`. Request the URL to the CDN node.

-   Using the parameter filtering feature, the CDN node initiates a request `http://www.abc.com/a.jpg` to the origin site ignoring parameter x=1.
-   After the origin site responds to the request, the response arrives at the CDN node. The CDN node keeps a copy and continues to respond the content of `http://www.abc.com/a.jpg` to the terminal. All similar requests `http://www.abc.com/a.jpg?parameters` respond the content of the CDN copy `http://www.abc.com/a.jpg`.
-   After you have disabled the parameter filtering feature, each URL caches a different copy on the CDN node. For example, different response content will be returned for `http://www.abc.com/a.jpg?x=1` and `http://www.abc.com/a.jpg?x=2` from the origin site.

## Procedure {#section_bb3_fpd_zdb .section}

1.  On the Domain Names page, select a domain, and click **Configure**.
2.  Go to **Optimization** \> **Parameter Filtering**, and click **Modify**.
3.  Click the **Parameter Filtering** switch.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13480/15456341974673_en-US.png)


