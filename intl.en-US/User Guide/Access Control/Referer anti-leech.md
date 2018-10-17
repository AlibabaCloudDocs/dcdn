# Referer anti-leech {#concept_ngj_5fd_zdb .concept}

## Introduction {#section_wbl_xfd_zdb .section}

-   The anti-leech feature is based on the referer information supported by HTTP. It uses the referer to track, identify, and judge sources. Users can configure the referer blacklist and whitelist for accesses to identify and filter a visitor’s identity, limiting their access to CDN resources.
-   The anti-leech feature supports blacklist or whitelist. After a visitor initiates a request for a resource, the request reaches the CDN node. The CDN node filters the visitor’s identity according to the preset anti-leech blacklist or whitelist. Visitors with an identity that is either included in the whitelist or not excluded in the blacklist can obtain the resource. Otherwise, the visitor request is rejected and a 403 response code is returned.

## Restrictions and guidelines {#section_xrd_1gd_zdb .section}

-   The anti-leech feature is disabled by default. You can configure it as needed.
-   Blacklist and whitelist are mutually exclusive. You can use this feature to edit only the referer blacklist or whitelist at a time.
-   You can set whether to allow **empty referer field** to access CDN resources. This allows direct access to the resource URL from the browser address bar.
-   After configuration, support for wildcard domains is automatically added. For example, if you enter example.com, the effective configuration is \*.example.com, applying to all subdomains of example.com.

## Procedure {#section_d5m_cgd_zdb .section}

1.  On the Domain Names page, select a domain name and click **Configure**.
2.  Go to **Access Control** \> **Referer Anti-leech**, and click **Modify**.

    ![](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/pic/65105/cn_zh/1533107870344/D14.jpg)

3.  Configure a **Blacklist** or **Whitelist**.

