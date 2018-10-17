# IP blacklist and whitelist {#concept_qj3_gfd_zdb .concept}

## Introduction {#section_ug4_hfd_zdb .section}

DCDN supports blacklist rules. An IP address that is listed on the blacklist cannot access the corresponding domain.

-   IP blacklist currently supports blacklisting entire IP address ranges, for example: 127.0.0.1/24.

-   For example, 127.0.0.1/24. 24 indicates that the first 24 bits in the subnet mask are used as effective bits,and 32-24=8 bits are used to express host numbers. In this way, the subnet can accommodate 2 ^ 8-2 = 254 hosts. 127.0.0.1/24 indicates the IP network segment in the range of 127.0.0.1 to 127.0.0.255.


## Procedure {#section_iwq_3fd_zdb .section}

1.  On the Domain Names page, select a domain name and click **Configure**.
2.  Go to **Access Control** \> **IP Blacklist**, and click **Modify**.

    ![](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/pic/65107/cn_zh/1533108143697/D15.jpg)

3.  Configure the IP blacklist and then click OK.

