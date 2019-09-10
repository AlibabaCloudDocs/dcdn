# 开通IP应用加速 {#task_187634 .task}

本文为您介绍了如何开通IP应用加速。IP应用加速功能为您提供网络传输加速，降低服务的延迟和提升访问的可用性。

您需要先开通全站加速服务，详情请参见[步骤一：开通服务](../../../../cn.zh-CN/快速入门/步骤一：开通服务.md#)。

1.  登录[全站加速控制台](https://dcdn.console.aliyun.com/overview)。
2.  进入IP应用加速页面，单击**开通IP应用加速**。 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/217945/155788567047180_zh-CN.png)

3.  选择适合您的**计费方式**，单击**立即开通**。 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/217945/155788567047183_zh-CN.png)

4.  返回到IP应用加速页面，单击**添加域名**。 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/217945/155788567047184_zh-CN.png)

5.  在添加域名页面，根据您的需求，填写对应项，业务类型请选择**IP应用加速**，单击**下一步**。 

    **说明：** 目前只支持添加一个端口，如果您想要添加多个端口，请您[提交工单](https://selfservice.console.aliyun.com/ticket/createIndex)。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/217945/155788567047185_zh-CN.png)

6.  在域名列表页面，状态显示为正常运行即表示您添加域名成功。此时记录下对应的CNAME值就可以在DNS服务的后台管理里面，将加速域名的解析指向该CNAME值，即可体验IP应用加速的服务。配置CNAME，详情请参见[步骤三：配置CNAME](../../../../cn.zh-CN/快速入门/步骤三：配置CNAME.md#)。 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/217945/155788567047174_zh-CN.png)


