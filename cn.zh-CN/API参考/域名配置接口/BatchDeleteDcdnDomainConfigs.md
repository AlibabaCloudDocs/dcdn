# BatchDeleteDcdnDomainConfigs {#doc_api_dcdn_BatchDeleteDcdnDomainConfigs .reference}

调用BatchDeleteDcdnDomainConfigs批量删除域名配置。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=dcdn&api=BatchDeleteDcdnDomainConfigs&type=RPC&version=2018-01-15)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|BatchDeleteDcdnDomainConfigs|操作接口名，系统规定参数。取值：**BatchDeleteDcdnDomainConfigs**。

 |
|DomainNames|String|是|example.com|您的加速域名，多个用逗号（,）分隔。

 |
|FunctionNames|String|是|referer\_white\_list\_set,https\_force|功能列表名称，用逗号（,）分隔。

 |

功能说明

|名称

|说明

|
|----|----|
|referer\_white\_list\_set

|refer白名单

|
|referer\_black\_list\_set

|refer黑名单

|
|filetype\_based\_ttl\_set

|文件过期时间设置

|
|path\_based\_ttl\_set

|目录过期时间设置

|
|cc\_defense

|防CC攻击

|
|oss\_auth

|OSS鉴权Bucket

|
|ip\_black\_list\_set

|IP黑名单

|
|ip\_white\_list\_set

|IP白名单

|
|error\_page

|错误页面重定向

|
|tesla

|页面优化加速

|
|set\_req\_host\_header

|修改回源自定义头

|
|set\_hashkey\_args

|忽略url参数

|
|aliauth

|阿里鉴权

|
|set\_resp\_header

|设置响应头（浏览器端可见）

|
|video\_seek

|视频切片拖拽开关

|
|range

|Range请求功能

|
|gzip

|页面Gzip优化

|
|https\_force

|强制HTTPS跳转

|
|http\_force

|强制HTTP跳转

|
|alilive

|视频直播配置

|
|forward\_scheme

|自适应回源

|

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|04F0F334-1335-436C-A1D7-6C044FE73368|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://dcdn.aliyuncs.com/?Action=BatchDeleteDcdnDomainConfigs
&DomainNames=example.com
&FunctionNames=referer_white_list_set,https_force
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<BatchDeleteDcdnDomainConfigsResponse>
	  <RequestId>04F0F334-1335-436C-A1D7-6C044FE73368</RequestId>
</BatchDeleteDcdnDomainConfigsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"04F0F334-1335-436C-A1D7-6C044FE73368"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|Invalid%s.ValueNotSupported|FunctionName \[%s\] is not supported.|不支持该配置，请重新查询。|

访问[错误中心](https://error-center.aliyun.com/status/product/dcdn)查看更多错误码。

