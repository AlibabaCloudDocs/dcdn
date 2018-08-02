# IP黑白名单 {#concept_qj3_gfd_zdb .concept}

## 功能介绍 {#section_ug4_hfd_zdb .section}

支持黑名单规则，添加了黑名单的IP，表示此IP无法访问当前加速域名。

-   IP黑名单当前支持ip网段添加，例如：127.0.0.1/24。

-   例如：127.0.0.1/24 24表示采用子网掩码中的前24位为有效位，即用32-24=8bit来表示主机号，该子网可以容纳2^8 - 2 = 254 台主机。故127.0.0.1/24 表示IP网段范围是：127.0.0.1~127.0.0.255。


## 操作步骤 {#section_iwq_3fd_zdb .section}

1.  在 域名管理 页，选择域名，单击 **配置**。
2.  在 **访问控制** \> **IP黑名单** 栏，单击 **修改配置**。

    ![](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/pic/65107/cn_zh/1533108143697/D15.jpg)

3.  添加IP后确认开启。

