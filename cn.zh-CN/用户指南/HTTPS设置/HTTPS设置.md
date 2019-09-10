# HTTPS设置 {#concept_q1h_wzb_zdb .concept}

## 功能介绍 {#section_vxj_xzb_zdb .section}

HTTPS是以安全为目标的HTTP通道，即将HTTP用SSL/TLS协议进行封装，可以称为HTTP的安全版。HTTPS的安全基础是SSL/TLS协议。

-   HTTPS加速优势：
    -   传输过程中对用户的关键信息进行加密，防止类似Session ID或者Cookie内容被攻击者捕获，造成敏感信息泄露等安全问题。
    -   传输过程中对数据进行完整性校验，防止DNS或内容遭第三方劫持、篡改等中间人攻击（MITM）。了解更多，[使用HTTPS防止流量劫持](http://yq.aliyun.com/articles/2666)。
-   阿里云CDN提供HTTPS安全加速方案，仅需开启HTTPS后上传证书/私钥即可使用。同时，支持用户对证书进行查看、停用、启用、编辑等操作。

-   您可以在[阿里云云盾](https://yundun.console.aliyun.com/?spm=5176.8232292.0.0.6ae69859iVmFyo&p=cas#/cas/home)快速申请免费证书或购买高级证书。在阿里云云盾购买的证书，可在CDN控制台直接选择，无需上传。

-   证书配置正确及开启状态，同时支持HTTP访问和HTTPS访问。证书不匹配或者停用证书，仅支持HTTP访问。

-   目前不支持SNI 回源。

## 注意事项 {#section_fls_cdc_zdb .section}

配置相关：

-   支持泛域名HTTPS服务。

-   支持该功能的“停用”和“启用”。

    -   启用：支持修改证书，默认兼容用户的HTTP和HTTPS请求，支持**强制跳转**设置。
    -   停用：不支持HTTPS请求且将不再保留证书/私钥信息，再次开启证书，需要重新上传证书/私钥。
-   允许用户查看证书。但由于私钥信息敏感，不支持私钥查看，请妥善保管证书相关信息。

-   支持修改、编辑证书。但生效时间大约为10分钟，请慎重操作。


计费相关：

HTTPS安全加速属于增值服务，开启后将产生HTTPS请求数计费。当前计费标准详见[HTTPS计费详情](https://www.aliyun.com/price/product#/dcdn/detail)。

**说明：** HTTPS根据请求数单独计费，费用不包含在CDN流量包或预付费套餐里。请确保账户余额充足后，再开通HTTPS服务，以免因此欠费，影响CDN服务。

证书相关：

-   开启 HTTPS安全加速 功能的加速域名，须要上传证书，包含证书/私钥，均为 PEM 格式。 参见[证书格式说明](https://www.alibabacloud.com/help/doc-detail/65102.htm)。

    **说明：** CDN采用的Tengine服务是基于Nginx的，因此只支持Nginx能读取的证书，即PEM格式。

-   只支持带SNI信息的SSL/TLS握手。
-   您上传的证书和私钥要匹配，否则会校验出错。
-   更新证书的生效时间约为10分钟。
-   不支持带密码的私钥。

## 操作步骤 {#section_qgh_5dc_zdb .section}

1.  购买证书。

    开启HTTPS安全加速，需要您具备匹配加速域名的证书。您可以在[阿里云云盾](https://yundun.console.aliyun.com/?spm=5176.8232292.0.0.6ae69859iVmFyo&p=cas#/cas/home)快速申请免费的证书或购买高级证书。

2.  加速域名配置。
    1.  在域名管理页，选择域名，单击**管理**。
    2.  在**HTTPS配置** \> **HTTPS证书**栏，单击**修改配置**。
    3.  打开**HTTPS安全加速**开关。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13469/15586708254540_zh-CN.png)

        **说明：** HTTPS安全加速属于增值服务，开启后将产生HTTPS请求数计费，了解[计费详情](https://cn.aliyun.com/price/product#/dcdn/detail)。

    4.  选择证书。
        -   您可以在[阿里云盾证书服务](https://yundun.console.aliyun.com/?p=cas#/cas/home)快速申请免费证书或购买高级证书。 云盾的证书，可以通过证书名称直接选择适配该加速域名。

        -   若证书列表中无当前适配的证书可以选择自定义上传，需要设置证书名称后上传证书内容和私钥，该证书将会在**云盾证书服务**中保存，可以在**我的证书**部分查看。

        -   仅支持PEM的证书格式，了解更多。[证书格式说明](intl.zh-CN/用户指南/HTTPS设置/证书格式说明.md#)。
    5.  支持设置 **强制跳转**：自定义将用户的原请求方式进行强制跳转。

        例如开启 **强制HTTPS跳转** 后，用户发起了一个HTTP请求，服务端返回302重定向响应，原来的HTTP请求强制重定向为HTTPS请求。

        -   默认：兼容用户的HTTP和HTTPS请求。
        -   强制HTTPS跳转：用户的请求将强制重定向为HTTPS请求。
        -   强制HTTP跳转：用户的请求将强制重定向为HTTP请求。
3.  验证证书是否生效。

    设置完成待证书生效后（设置HTTPS证书后约1小时后生效），使用HTTPS方式访问资源。如果浏览器中出现绿色HTTPS标识，表明当前与网站建立的是私密连接，HTTPS安全加速生效。如下图：

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13469/155867082544183_zh-CN.png)


