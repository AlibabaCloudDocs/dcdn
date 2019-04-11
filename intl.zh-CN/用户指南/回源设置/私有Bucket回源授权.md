# 私有Bucket回源授权 {#concept_hk4_l5w_ydb .concept}

## 功能介绍 {#section_wzm_t5w_ydb .section}

私有Bucket回源授权指若加速域名想要回源至您账号下标记为私有Bucket，需要首先进行授权。授权成功并开启授权配置后，您开启的私有Bucket授权的域名才有权限访问私有Bucket。

## 风险提示 {#section_zqh_55w_ydb .section}

-   授权成功并开启了对应域名的私有Bucket功能，该加速域名可以访问您的私有Bucket内的资源内容。开启该功能前，请根据实际的业务情况，谨慎决策。

    **说明：** 若您授权的私有Bucket内容并不适合作为CDN加速域名的回源内容，请勿授权或者开启该功能。

-   您可以配合使用CDN提供的OSS防盗链\(Referer\)、鉴权等功能，有效保护您的资源安全。
-   若您的网站有攻击风险，请购买高防服务。同时，请勿授权或开启私有OSS Bucket功能。

## 操作步骤 {#section_kcw_y5w_ydb .section}

-   **开启私有 Bucket回源授权**
    1.  登录[CDN控制台](https://cdnnext.console.aliyun.com)，在域名管理页，选择域名，单击**管理**。
    2.  在**基本配置** \> **源站信息**区域框，单击**修改配置**，设置源站类型为**OSS域名**。
    3.  在**回源配置** \> **私有Bucket回源设置**区域框，单击**点击授权**。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13458/15549543434403_zh-CN.png)

    4.  单击**同意授权**，授权成功。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13458/15549543434404_zh-CN.png)

    5.  打开**私有Bucket回源**开关，该域名开启私有Bucket回源配置成功。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13458/15549543434405_zh-CN.png)

-   **关闭私有Bucket回源授权**
    1.  登录[RAM控制台](https://ram.console.aliyun.com)，单击**RAM角色管理**。
    2.  删除**AliyunCDNAccessingPrivateOSSRole**授权。
    3.  私有bucket授权删除成功。

        **说明：** 若您的加速域名正在使用私有 Bucket做为源站进行回源，请不要关闭或删除私有 Bucket授权。


