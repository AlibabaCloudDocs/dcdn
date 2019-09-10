# Back-to-Source settings {#concept_xpz_3sw_ydb .concept}

## Introduction {#section_jvd_lsw_ydb .section}

You can configure the domain name of the web server to be accessed during the origin fetch process.

-   The origin host configuration is optional. The default value is as follows:
    -   If the origin site is an **IP** address, the origin host is the DCDN domain name by default.
    -   If the origin site is an **OSS domain name**, the origin host is the origin site domain name by default.
-   The options are: DCDN domain names, origin domain names, and custom domain names.

    **Note:** SNI origin fetch is not currently supported.


## Procedure {#section_hqx_4sw_ydb .section}

1.  On the Domain Names page, select a domain name, and click **Configure**.
2.  Go to **Origin Fetch** \> **Origin Host**, and click **Modify**.
3.  Select the type of domain name to speed up, and click **OK**.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13456/154563055834872_en-US.png)

## Difference between the origin site and the origin host {#section_o4x_ysw_ydb .section}

-   Origin site: The origin site determines the specific IP address that is requested for origin fetch.

-   Origin host: The origin host determines the specific website that is at the IP address accessed by the origin fetch request.


|Case|Case 1|Case 2|
|:---|:-----|:-----|
|Origin site|www.a.com|1.1.1.1|
|Origin host|www.b.com|www.b.com|
|In actual origin fetch, the request is forwarded to|Website www.b.com on the host corresponding to www.a.com|Website www.b.com on the host that is corresponding to 1.1.1.1|

