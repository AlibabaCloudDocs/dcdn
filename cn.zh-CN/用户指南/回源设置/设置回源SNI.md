# 设置回源SNI {#task_727378 .task}

如果您的源站IP绑定了多个域名，当全站加速节点以HTTPS协议访问您的源站时，您可以参照本文档，设置回源SNI指明具体访问的域名。

服务器名称指示 Server Name Indication（SNI）是一个扩展的传输层安全性协议 Transport Layer Security（TLS）。在该协议下，握手过程开始时，客户端会告诉它正在连接的那台服务器即将要连接的主机名称，以允许该服务器在相同的IP地址和TCP端口号上呈现多个证书，即一台服务器可以为多个域名提供服务。因此，同一个IP地址上提供的多个安全的HTTPS网站（或其他任何基于TLS的服务），不需要使用相同的证书。

但是，如果您的源站服务器使用单个IP提供多个域名的HTTPS服务，且您已经为您的全站加速设置了以443端口回源（全站加速节点以HTTPS协议访问您的服务器），您就需要设置回源SNI，指明所请求的具体域名。这样全站加速节点以HTTPS协议回源访问您的服务器时，服务器才会正确地返回对应的证书。

**说明：** 如果您的源站是阿里云OSS的，则无需设置回源SNI。

工作原理

回源SNI的工作原理如下图所示：

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/583059/156093502749575_zh-CN.png)

1.  全站加速节点以HTTPS协议访问源站时，在SNI中指定访问的域名。
2.  源站接收到请求后，根据SNI中记录的域名，返回对应域名的证书。
3.  全站加速节点收到证书，与服务器端建立安全连接。

1.  登录[全站加速控制台](https://dcdn.console.aliyun.com/overview)。
2.  在左侧导航栏，单击**域名管理**。
3.  在您需要设置的域名右侧，单击**配置**。
4.  在左侧导航栏，单击**回源配置**。
5.  在回源SNI区域框，单击**修改配置**。 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/583059/156093502749573_zh-CN.png)

6.  打开**回源SNI开关**，填入您服务器源站提供服务的具体域名，单击**确认**，完成配置。 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/583059/156093502749574_zh-CN.png)


