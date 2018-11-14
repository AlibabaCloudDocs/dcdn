# Use the same protocol as the back-to-source protocol {#concept_g1m_ftw_ydb .concept}

## Introduction {#section_hqc_ptw_ydb .section}

When this feature is used, the client protocol for origin fetch is consistent with the protocol for accessing resources. That is, if a client uses HTTPS to request a resource, when the resource is not cached on the node, DCDN requests the resource from the origin using HTTPS. Similarly, if a client uses HTTP to request the resource, the node also uses HTTP to forward the request to the origin.

Currently, Dynamic Origin Protocol Policy and Static Origin Protocol Policy are supported.

**Note:** The origin site must support both port 80 and port 443. Otherwise, an origin fetch failure may occur.

## Procedure {#section_h1k_5tw_ydb .section}

Dynamic Origin Protocol Policy

1.  On the Domain Names page, select a domain name, and click **Configure**.
2.  Go to **Acceleration Rules** \> **Dynamic Origin Protocol Policy**, and click **Modify**.
3.  ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13457/15421634694392_en-US.png)
4.  Select a Redirect Type: **Match Client**, **HTTP**, or **HTTPS**.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13457/15421634694393_en-US.png)

Static Origin Protocol Policy

1.  On the Domain Names page, select a domain name, and click **Configure**.
2.  Go to **Origin Fetch** \> **Static Origin Protocol Policy** and click the switch.
3.  ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13457/15421634694395_en-US.png)

