# UsageAgent黑/白名单 {#task_727365 .task}

本文档为您介绍了UsageAgent黑/白名单原理、使用场景和控制台操作步骤。您可以配置UsageAgent黑/白名单功能，全站加速节点服务器会根据您请求的Usage-Agent字段进行黑白名单的管理。

当您需要根据请求的Usage-Agent字段进行访问控制，请配置UsageAgent黑/白名单功能，实现对请求过滤。

**说明：** 

-   User-Agent规则不区分大小写，且支持 `*`通配符。例如：`*curl*|*IE*|*chrome*|*firefox*`，多个值用`|`分割。
-   黑白名单互斥，只支持同时启用其中一个名单。

1.  登录[全站加速控制台](https://dcdn.console.aliyun.com/overview)。
2.  在左侧导航栏，单击**域名管理**。
3.  在您需要设置的域名，单击**配置**。
4.  在左侧导航栏，单击**访问控制**。
5.  在UserAgent黑/白名单区域框中，单击修改配置。
6.  根据您的需求配置黑白名单的规则，单击**确定**。 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/583051/156093343249571_zh-CN.png)


