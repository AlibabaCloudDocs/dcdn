# Referer anti-leech {#concept_ngj_5fd_zdb .concept}

## Introduction {#section_wbl_xfd_zdb .section}

-   The anti-leech feature is based on the referer information supported by HTTP. It uses the referer to track, identify, and judge sources. Users can configure the referer blacklist and whitelist for accesses to identify and filter a visitor’s identity, limiting their access to DCDN resources.
-   The anti-leech feature supports blacklist or whitelist. After a visitor initiates a request for a resource, the request reaches the DCDN node. The DCDN node filters the visitor’s identity according to the preset anti-leech blacklist or whitelist. Visitors with an identity that is either included in the whitelist or not excluded in the blacklist can obtain the resource. Otherwise, the visitor request is rejected and a 403 response code is returned.

## Restrictions and guidelines {#section_xrd_1gd_zdb .section}

-   The anti-leech feature is disabled by default. You can configure it as needed.
-   Blacklist and whitelist are mutually exclusive. You can use this feature to edit only the referer blacklist or whitelist at a time.
-   You can set whether to allow **empty referer field** to access DCDN resources. This allows direct access to the resource URL from the browser address bar.
-   After configuration, support for wildcard domains is automatically added. For example, if you enter example.com, the effective configuration is \*.example.com, applying to all subdomains of example.com.

## Procedure {#section_d5m_cgd_zdb .section}

1.  On the Domain Names page, select a domain name and click **Configure**.
2.  Go to **Access Control** \> **Referer Anti-leech**, and click **Modify**.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13475/154563076434859_en-US.png)
3.  Configure a **Blacklist** or **Whitelist**.

