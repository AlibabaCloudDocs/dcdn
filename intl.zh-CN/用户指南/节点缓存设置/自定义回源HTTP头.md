# 自定义回源HTTP头 {#concept_fv2_byb_zdb .concept}

## 功能介绍 {#section_ohk_dyb_zdb .section}

|参数|解释|
|:-|:-|
|Content-Type|指定客户程序响应对象的内容类型|
|Cache-Control|指定客户程序请求和响应遵循的缓存机制|
|Content-Disposition|指定客户程序响应对象时激活文件下载设置默认的文件名|
|Content-Language|指定客户程序响应对象的语言|
|Expires|指定客户程序响应对象的过期时间|
|Access-Control-Allow-Origin|指定允许的跨域请求的来源|
|Access-Control-Allow-Methods|指定允许的跨域请求方法|
|Access-Control-Max-Age|指定客户程序对特定资源的预取请求返回结果的缓存时间|
|Access-Control-Expose-Headers|指定允许访问的自定义头信息|

可设置http响应头。目前提供9个http请求头参数可供自行定义取值。参数解释如下：

## 注意事项 {#section_dwh_hyb_zdb .section}

-   HTTP响应头的设置会影响该加速域名下所有资源客户程序（例如浏览器）的响应行为，但不会影响缓存服务器的行为。
-   目前仅支持这些http头参数取值设置。有其他HTTP头部设置需求，请提工单反馈。
-   Access-Control-Allow-Origin参数的取值，支持 `*` \(表示全部域名\)或者完整域名。例如：`www.aliyun.com`。目前不支持泛域名设置。

## 操作步骤 {#section_odq_myb_zdb .section}

1.  在 域名管理页，选择域名，单击 **修改配置**。
2.  在 **缓存配置** \> **HTTP头** 栏，单击 **添加**。

    ![](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/pic/65094/cn_zh/1533105460668/D8.png)

3.  您可以自定义选择参数和取值，设置HTTP头。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13466/15331989384465_zh-CN.png)


