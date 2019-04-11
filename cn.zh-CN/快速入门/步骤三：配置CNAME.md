# 步骤三：配置CNAME {#task_alv_1fk_xdb .task}

使用全站加速服务，需要通过添加CNAME记录，将您的加速域名指向**阿里云提供的CNAME地址**，这样访问加速域名的请求才能转发到CDN节点上，达到加速效果。

配置CNAME需前往你的域名解析服务商\(如阿里云解析、DNSPod、新网等\)，本文档以**域名在阿里云解析** 为例：

1.   获取加速域名的CNAME值 

    在全站加速控制台**域名管理**的域名列表中复制加速域名对应的CNAME值：

2.  添加CNAME记录 
    1.  步骤一：在阿里云解析[域名解析控制台](https://dc.console.aliyun.com/dns/?spm=5176.200001.0.0.pbY4Je)， 进入对应域名的解析页。选择**解析设置**：

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13449/155495469635117_zh-CN.png)

    2.  请按如下参数设置：

        -   记录类型：`CNAME`。

        -   主机记录：加速域名的前缀。\(例如要添加的加速域名是`test.example.com`，则前缀为`test`\)。

        -   记录值：步骤1复制的`CNAME`值。

        -   解析线路和TTL：默认值。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13449/155495469635118_zh-CN.png)

    3.  步骤三：单击**确认**，配置CNAME完毕。全站加速服务将在CNAME配置生效后立即生效。

        **说明：** 

        -   新增CNAME记录会实时生效，而修改CNAME记录可能需要最多72小时的生效时间。
        -   如遇添加冲突，可考虑换一个加速域名，或参考 [解析记录互斥规则](https://help.aliyun.com/knowledge_detail/39787.html?spm=a2c4g.11186623.2.4.KAwlRA)自行调整冲突的记录。

        -   全站加速默认使用纯动态加速，静态资源也不会缓存，全部回源获取。需通过配置 [动静态资源规则](../../../../../cn.zh-CN/用户指南/动静态加速规则/设置静态文件类型.md#)指定静态文件的类型，实现动、静态资源分别使用动、静态加速，达到最好的加速效果。

3.  生效验证 

    配置CNAME后，不同的DNS服务商的CNAME生效的时间也不同。

    您可以`ping`或`dig`您所添加的加速域名。如果被转向`*.*kunlun*.com`，即表示CNAME配置已经生效，全站加速服务也已生效：

    ![](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/pic/64928/cn_zh/1517391265133/77.png)


