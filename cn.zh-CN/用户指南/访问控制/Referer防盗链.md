# Referer防盗链 {#concept_ngj_5fd_zdb .concept}

## 功能介绍 {#section_wbl_xfd_zdb .section}

-   防盗链功能基于 HTTP 协议支持的 Referer 机制，通过 Referer 跟踪来源，对来源进行识别和判断。用户可以通过配置访问的 referer 黑白名单，对访问者身份进行识别和过滤，从而限制 CDN 资源被访问的情况。
-   目前防盗链功能支持黑名单或白名单机制。访客对资源发起请求后，请求到达 CDN 节点，CDN节点会根据用户预设的防盗链黑名单或白名单，对访客的身份进行过滤。符合规则可以顺利请求到资源，否则该访客请求将被禁止，返回403响应码。

## 注意事项 {#section_xrd_1gd_zdb .section}

-   系统默认不启用，您可以自行选择是否配置。
-   黑白名单互斥。开启功能后，您只能选择编辑Refer黑名单或者白名单，同一时间只支持一种方式。
-   支持设置是否允许**空 Referer 字段**访问CDN资源。（即允许通过浏览器地址栏直接访问资源URL。）
-   配置后会自动添加泛域名支持，例如填写a.com，则最终配置生效的是\*.a.com，所有子级域名都会生效。

## 操作步骤 {#section_d5m_cgd_zdb .section}

1.  在 域名管理页，选择域名，单击**配置**。
2.  在 **访问控制** \> **Refer防盗链** 栏，单击 **修改配置**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13475/4606_zh-CN.png)

3.  点单击选择 **白名单**或 黑**名单**。

