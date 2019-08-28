# User-Agent黑白名单 {#task_727365 .task}

您可以通过配置User-Agent黑名单和白名单来实现对访客身份的识别和过滤，从而限制访问DCDN资源的用户，提升DCDN的安全性。通过本文您可以了解User-Agent黑/白名单的配置方法。

当您需要根据请求的User-Agent字段进行访问控制时，请配置User-Agent黑/白名单功能，实现对请求过滤。

-   User-Agent黑名单：黑名单内的User-Agent字段均无法访问当前资源。

    如果您的User-Agent字段被加入黑名单，该带有User-Agent字段的请求仍可访问到DCDN节点，但是会被DCDN节点拒绝并返回403，DCDN日志中仍会记录这些黑名单中的User-Agent字段请求记录。

-   User-Agent白名单：只有白名单内的User-Agent字段才能访问当前资源，白名单以外的User-Agent字段均无法访问当前资源。

1.  登录[全站加速控制台](https://dcdn.console.aliyun.com/overview)。
2.  在左侧导航栏，单击**域名管理**。
3.  在您需要设置的域名，单击**配置**。
4.  在左侧导航栏，单击**访问控制**。
5.  在UserAgent黑/白名单区域框中，单击修改配置。
6.  根据您的需求配置黑白名单的规则，单击**确定**。 

    ![UA规则设置](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/583051/156698435849571_zh-CN.png)


