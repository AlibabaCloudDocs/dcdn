# Set priorities for multiple sources {#concept_n5c_4rw_ydb .concept}

## Introduction {#section_lqd_rrw_ydb .section}

DCDN allows you to set the origin priority for both **dynamic resources** and **static resources**.

-   DCDN supports three types of origin domain names; OSS domain names, IP, and origin domain names. Multiple IP addresses and origin domain names are supported. You can set the origin priority when multiple origin sites exist.

-   When you specify IP or origin domain as the origin type, you can configure multiple origin sites and set the origin priorities. The origin priority can be Primary or Secondary, and Primary has higher priority than Secondary.

-   100% of the user’s origin fetch traffic is first sent back to the origin site with higher priority.

    -   If an origin site fails the health check for three consecutive times, all traffic is directed to lower-priority origin sites.
    -   If the origin site passes the health check, it is marked as available again and restored to its the original priority.
    -   When all origin sites have the same origin priority, CDN round-robin takes place.

Origin site health check: 4-layer health check is automatically performed on origin sites every 5 seconds.

Supported scenario: Primary-secondary origin switchover.

## Procedure {#section_ubj_vrw_ydb .section}

1.  On the Domain Names page, select a domain name, and click **Configure**.
2.  Go to **Basic Settings** \> **Origin Information**, and click **Modify**.
3.  Set the origin **IP** and **Priority**.

    ![](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/pic/65091/intl_zh/1533110759243/D21.jpg)

4.  Click **OK** for the settings to take effect.

    **Note:** Priority settings for multiple origin sites only support the IP and origin domain names. OSS domain names do not support the origin priority setting. Select the origin type that suits your needs and set the priority appropriately.


