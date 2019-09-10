# Force redirect {#concept_hrh_hdd_zdb .concept}

## Introduction {#section_n33_ndd_zdb .section}

When **SSL acceleration** is enabled for a DCDN domain, DCDN can redirect user requests according to the force redirect setting.

For example, you set the redirect type to **HTTP to HTTPS**. When the user initiates an HTTP request, the server returns a 302 redirect response, and the original HTTP request is redirect to the HTTPS, as shown in the following figure:

![](images/4571_en-US.png)

**Note:** 

-   For the force redirect setting to take effect, make sure that **SSL acceleration** has been enabled. You can redirect HTTP to HTTPS or redirect HTTPS to HTTP.
-   User request are not redirected by default.

## Procedure {#section_lpg_sdd_zdb .section}

1.  On the Domain Names page, select a domain name, and click **Configure**.
2.  Go to **HTTPS Settings** \> **Force Redirect**, and click **Modify**.
3.  Select a Redirect Type.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13471/15456338024572_en-US.png)

    -   The force redirect setting is optional. The default setting supports both HTTP and HTTPS requests.
    -   The options are Default, HTTPS to HTTP, HTTP to HTTPS.
        -   HTTP to HTTPS: HTTP requests are redirected to HTTPS.
        -   HTTPS to HTTP: HTTPS requests are redirected to HTTP.

