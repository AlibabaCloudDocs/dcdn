# UpdateDcdnDomain {#doc_api_dcdn_UpdateDcdnDomain .reference}

调用UpdateDcdnDomain修改加速域名。

创建加速域名之前，必须先开通全站加速服务。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=dcdn&api=UpdateDcdnDomain&type=RPC&version=2018-01-15)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|UpdateDcdnDomain|操作接口名。系统规定参数，取值：**UpdateDcdnDomain**。

 |
|DomainName|String|是|example.com|需要接入全站加速的域名。

 |
|ResourceGroupId|String|否|123|资源组ID。

 |
|Sources|String|否|\[\{"content":"1.1.1.1","type":"ipaddr","priority":"20","port":80\}\]|回源地址列表。

 |
|TopLevelDomain|String|否|yourTopLevelDomain|顶级接入域。

 |

Sources各字段含义如下所示。

|参数

|类型

|是否必选

|描述

|
|----|----|------|----|
|type

|String

|是

|源站类型，取值：ipaddr：IP源站；domain：域名源站；oss：OSS Bucket为源站。

|
|content

|String

|是

|回源地址，可以是IP或域名。

|
|port

|Integer

|否

|可以指定443、80端口，也可以自定义端口，默认值80。443走https回源。

|
|priority

|String

|否

|源站地址对应的优先级，支持20和30，默认20。20是主，30是备。

|
|weight

|String

|否

|回源权重，100以内，默认10。

|

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|0AEDAF20-4DDF-4165-8750-47FF9C1929C9|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://dcdn.aliyuncs.com?Action=UpdateDcdnDomain
&SourceType=domain
&Sources=[{"content":"1.1.1.1","type":"ipaddr","priority":"20","port":80}]
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<UpdateDcdnDomainResponse>
	  <RequestId>0AEDAF20-4DDF-4165-8750-47FF9C1929C9</RequestId>
</UpdateDcdnDomainResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"0AEDAF20-4DDF-4165-8750-47FF9C1929C9"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|MissingDomainName|The domainName parameter is required.|请填写域名参数。|
|400|InvalidDomainName.Malformed|The specified DomainName is invalid.|域名格式错误。|
|400|InvalidSource.Content.Malformed|The specified Source Content is invalid.|源站信息错误，请重新填写。|
|400|InvalidTypeContent.Mismatch|The specified source type does not match the specified source content.|源站类型和源站不匹配，请重新填写。|
|400|MissingSource.Content|The Source Content must be specified.|Source Content必填，请填写后重试。|
|400|MissingSource.Type|The Source Type must be specified.|Source Type必填，请填写后重试。|
|400|InvalidSource.Type.Malformed|The specified Source Type is invalid.|Source Type格式错误，请重新填写。|
|400|InvalidSource.Priority.Malformed|The specified Source Priority is invalid.|Source Priority格式错误，请填写正确的格式。|
|400|InvalidResourceGroupId.Malformed|The specified ResourceGroupId is invalid.|ResourceGroupId错误，请填写正确的ResourceGroupId。|
|400|EntityNotExists.ResourceGroup|The resource group does not exist.|该资源组不存在。|
|400|InvalidStatus.ResourceGroup|The current status of the resource group does not support this operation.|资源组当前状态不允许进行此操作。|
|403|DomainInProtectedMode|The domain is in protection mode. To request permission, contact Customer Service.|此域名处于被保护模式。如果您想做这个操作，请联系我们。|
|400|TopLevelDomain.NotFound|The specified TopLevelDomain does not exist.|顶级接入域不存在。|

访问[错误中心](https://error-center.aliyun.com/status/product/dcdn)查看更多错误码。

