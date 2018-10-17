# Use the same protocol as the back-to-source protocol {#concept_g1m_ftw_ydb .concept}

## Introduction {#section_hqc_ptw_ydb .section}

When this feature is used, the client protocol for origin fetch is consistent with the protocol for accessing resources. That is, if a client uses HTTPS to request a resource, when the resource is not cached on the node, DCDN requests the resource from the origin using HTTPS. Similarly, if a client uses HTTP to request the resource, the node also uses HTTP to forward the request to the origin.

Currently, Dynamic Origin Protocol Policy and Static Origin Protocol Policy are supported.

**Note:** The origin site must support both port 80 and port 443. Otherwise, an origin fetch failure may occur.

## Procedure {#section_h1k_5tw_ydb .section}

Dynamic Origin Protocol Policy

1.  On the Domain Names page, select a domain name, and click **Configure**.
2.  Go to **Acceleration Rules** \> **Dynamic Origin Protocol Policy**, and click **Modify**.

    ![](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/pic/65089/cn_zh/1533190133437/D44.jpg)

3.  Select a Redirect Type: **Match Client**, **HTTP**, or **HTTPS**.

    ![](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/pic/65089/cn_zh/1533094023974/D2.jpg)


Static Origin Protocol Policy

1.  On the Domain Names page, select a domain name, and click **Configure**.
2.  Go to **Origin Fetch** \> **Static Origin Protocol Policy** and click the switch.

    ![](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/pic/65089/cn_zh/1533113815534/D31.jpg)


