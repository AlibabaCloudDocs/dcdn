# 私有OSS Bucket回源授权 {#concept_hk4_l5w_ydb .concept}

## 功能介绍 {#section_wzm_t5w_ydb .section}

私有OSS Bucket回源授权是指，若加速域名想要回源至该用户账号下标记为私有OSS Bucket （简称私有 Bucket），需要首先进行授权。授权成功并开启授权配置，且用户开启私有 Bucket授权的域名后，才有权限访问私有 Bucket。

## 风险提示 {#section_zqh_55w_ydb .section}

-   授权成功并开启了对应域名的私有 Bucket功能，该加速域名可以访问您的私有 Bucket内的资源内容。开启该功能前，请根据实际的业务情况，谨慎决策。

    **说明：** 若您授权的私有 Bucket内容并不适合作为CDN加速域名的回源内容，请勿授权或者开启该功能。

-   您可以配合使用CDN提供的 **OSS防盗链\(Referer\)**、**鉴权** 等功能，有效保护您的资源安全。
-   若您的网站有攻击风险，请购买高防服务。同时，请勿授权或开启私有OSS Bucket功能。

## 操作步骤 {#section_kcw_y5w_ydb .section}

开启私有 Bucket回源授权

1.  在 域名管理 页，选择域名，单击**配置**。
2.  在 **回源设置** \> **源站信息** 栏，单击**修改配置**。
3.  在**回源设置** \> **私有Bucket回源设置** \> **服务授权**，单击**立即授权**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13458/4403_zh-CN.png)

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13458/4404_zh-CN.png)

4.  授权成功。单击**确定**，为该域名开启私有 Bucket回源配置。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13458/4405_zh-CN.png)

5.  开启成功。

关闭私有 Bucket回源授权

1.  进入 **访问控制** \> **角色管理**。
2.  在准备删除的角色名称后，单击**删除**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13458/4406_zh-CN.png)

3.  私有bucket授权删除成功。

    **说明：** 若您的加速域名正在使用私有 Bucket做为源站进行回源，请不要关闭或删除私有 Bucket授权。


