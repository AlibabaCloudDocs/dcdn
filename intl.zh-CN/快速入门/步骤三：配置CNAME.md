# 步骤三：配置CNAME {#task_alv_1fk_xdb .task}

本文档以域名在阿里云解析服务商为例，为您介绍如何在万网配置CNAME。您在全站加速中添加域名后，阿里云全站加速会给您分配对应的CNAME地址。如果您想启用全站加速服务，需要将加速域名指向CNAME地址，因此访问加速域名的请求才能转发到CDN节点上，达到加速效果。

1.  获取加速域名的CNAME值。 
    1.  登录[全站加速控制台](https://dcdn.console.aliyun.com)。
    2.  单击**域名管理**。
    3.  在域名管理页面，复制加速域名对应的CNAME值。
2.  添加CNAME记录。 
    1.  登录[域名解析控制台](https://dc.console.aliyun.com/dns/?spm=5176.200001.0.0.pbY4Je)。
    2.  在域名解析页面，单击目标域名后的**解析设置**。 

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13449/155860589935117_zh-CN.png)

    3.  单击**添加记录**，添加CNAME记录。 

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13449/155860589935118_zh-CN.png)

        -   记录类型：`CNAME`。
        -   主机记录：加速域名的前缀。

            |如果您的加速域名为...|主机记录为...|
            |:-----------|:-------|
            |`testcdn.aliyun.com`|`testcdn`|
            |`www.aliyun.com`|`www`|
            |`aliyun.com`|`@`|
            |`*.aliyun.com`|`*`|

        -   记录值：您进行步骤1时复制的CNAME值。
        -   解析线路：默认值。
        -   TTL：默认值。
    4.  单击**确认**，配置CNAME完毕。CNAME配置生效后，全站加速服务也会立即生效。 

        **说明：** 

        -   新增CNAME记录会实时生效，修改CNAME记录会在72小时之内生效。
        -   如果您遇到添加冲突问题，可以换一个加速域名或者调整冲突的记录，详情请参见[解析记录冲突判断规则](https://www.alibabacloud.com/help/zh/doc-detail/58456.htm)。

        -   全站加速默认使用纯动态加速，静态资源也不会缓存，全部回源获取。需通过配置[动静态资源规则](../../../../intl.zh-CN/用户指南/动静态加速规则/设置静态文件类型.md#)指定静态文件的类型，实现动、静态资源分别使用动、静态加速，达到最好的加速效果。
3.  验证CNAME配置是否生效。 

    配置CNAME后，不同的DNS服务商配置的CNAME生效时间不同。

    您可以通过使用ping或dig命令验证您所添加的加速域名，如果被转向`*.*kunlun*.com`，表示CNAME配置已经生效，全站加速服务也已生效。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13449/155860589947260_zh-CN.png)


