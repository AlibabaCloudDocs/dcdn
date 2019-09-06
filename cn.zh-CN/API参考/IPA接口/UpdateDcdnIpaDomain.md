# UpdateDcdnIpaDomain {#doc_api_dcdn_UpdateDcdnIpaDomain .reference}

调用UpdateDcdnIpaDomain修改加速域名。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=dcdn&api=UpdateDcdnIpaDomain&type=RPC&version=2018-01-15)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|UpdateDcdnIpaDomain|操作接口名，系统规定参数。取值：**UpdateDcdnIpaDomain**。

 |
|DomainName|String|是|example.com|需要接入全站加速IPA的域名。

 |
|ResourceGroupId|String|否|123|资源组ID。

 |
|Sources|String|否|\[\{"content":"1.1.1.1","type":"ipaddr","priority":"20","port":80,"weight":"15"\}\]|回源地址列表。

 |
|TopLevelDomain|String|否|yourDomain.com|顶级接入域。

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

|源站类型，取值：ipaddr：IP源站；domain：域名源站；oss：不支持oss。

|
|content

|String

|是

|回源地址，可以是IP或域名。

|
|port

|Integer

|否

|自定义端口，范围：0 ~ 65535。

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
|RequestId|String|15C66C7B-671A-4297-9187-2C4477247A74|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://dcdn.aliyuncs.com?Action=UpdateDcdnIpaDomain
&domainname=example.com
&SourceType=domain
&Sources=[{"content":"1.1.1.1","type":"ipaddr","priority":"20","port":80}]
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<UpdateDcdnIpaDomainResponse>
	  <RequestId>15C66C7B-671A-4297-9187-2C4477247A74</RequestId>
</UpdateDcdnIpaDomainResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"15C66C7B-671A-4297-9187-2C4477247A74"
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
|400|InvalidSource.Port.Malformed|The source port is empty, or it is outside the range 0-65535.|源站端口号为空，或者不在0-65535范围内。|
|403|DcdnIpaServiceNotFound|The DCDN IPA service has not been activated.|没有开通Dcdn Ipa服务。|

访问[错误中心](https://error-center.aliyun.com/status/product/dcdn)查看更多错误码。

