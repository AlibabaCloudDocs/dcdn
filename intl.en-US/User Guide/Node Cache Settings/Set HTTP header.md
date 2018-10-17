# Set HTTP header {#concept_fv2_byb_zdb .concept}

## Introduction {#section_ohk_dyb_zdb .section}

|Parameter|Description|
|:--------|:----------|
|Content-Type|Specifies the content type of a client response object.|
|Cache-Control|Specifies the caching method followed by client requests and responses.|
|Content-Disposition|Specifies the default file name for activating the file download settings when the client responds to objects.|
|Content-Language|Specifies the language for the client to respond to objects.|
|Expires|Specifies the expiration time for the client to respond to objects.|
|Access-Control-Allow-Origin|Specifies the sources of allowed cross-origin requests.|
|Access-Control-Allow-Methods|Specifies the method of allowed cross-origin requests.|
|Access-Control-Max-Age|Specifies the caching duration for the client program to return results for an origin fetch request for a specific resource.|
|Access-Control-Expose-Headers|Specifies custom header information of allowed access.|

You can set an HTTP response header. Currently, nine HTTP request header parameters are available for customization. The parameters are as follows:

## Restrictions and guidelines {#section_dwh_hyb_zdb .section}

-   The configuration of HTTP response header will affect the response actions of all resources’ client program under the DCDN domain name, rather than the actions of the cache server.
-   Currently, you can set the HTTP head only to the above mentioned parameters. To request other HTTP header parameter settings, open a ticket.
-   You can enter `*` to indicate all domain names or enter an absolute domain name for the Access-Control-Allow-Origin parameter. For example: `www.aliyun.com`. Currently, wildcard domain names are not supported.

## Procedure {#section_odq_myb_zdb .section}

1.  On the Domain Names page, select a domain name, and click **Configure**.
2.  Go to **Caching** \> **HTTP Header**, and click **Add**.

    ![](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/pic/65094/cn_zh/1533105460668/D8.png)

3.  You can set custom parameters for the HTTP header.

    ![](images/4465_en-US.png)


