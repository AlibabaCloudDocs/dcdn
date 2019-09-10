# StopDcdnIpaDomain {#doc_api_dcdn_StopDcdnIpaDomain .reference}

调用StopDcdnIpaDomain停用某个加速域名，将DomainStatus变更为offline。

停用该加速域名后，该条加速域名信息仍保留，针对加速域名的请求系统将做自动回源处理。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=dcdn&api=StopDcdnIpaDomain&type=RPC&version=2018-01-15)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|StopDcdnIpaDomain|操作接口名，系统规定参数。取值：**StopDcdnIpaDomain**。

 |
|DomainName|String|是|example.com|需要接入全站加速IPA的域名。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|15C66C7B-671A-4297-9187-2C4477247A74|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://dcdn.aliyuncs.com?Action=StopDcdnIpaDomain
    &DomainName=example.com
    &<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<StopDcdnIpaDomainResponse>
	  <RequestId>15C66C7B-671A-4297-9187-2C4477247A74</RequestId>
</StopDcdnIpaDomainResponse>
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
|403|DcdnIpaServiceNotFound|The DCDN IPA service has not been activated.|没有开通Dcdn Ipa服务。|

访问[错误中心](https://error-center.aliyun.com/status/product/dcdn)查看更多错误码。

