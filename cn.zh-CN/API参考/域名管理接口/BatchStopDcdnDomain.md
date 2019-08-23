# BatchStopDcdnDomain {#doc_api_dcdn_BatchStopDcdnDomain .reference}

停用加速域名，将DomainStatus变更为offline。

停用该加速域名后，该条加速域名信息仍保留，针对加速域名的请求系统将做自动回源处理。

如果暂时不需要对某域名进行加速，推荐使用StopDomain接口，暂停域名加速效果。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=dcdn&api=BatchStopDcdnDomain&type=RPC&version=2018-01-15)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|BatchStopDcdnDomain|操作接口名。系统规定参数。取值：**BatchStopDcdnDomain**。

 |
|DomainNames|String|是|test.com|需要接入全站加速的域名，多个用逗号（,）分隔。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|0AEDAF20-4DDF-4165-8750-47FF9C1929C9|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://dcdn.aliyuncs.com?Action=BatchStopDcdnDomain
&DomainNames=test.com
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<BatchStopDcdnDomainResponse>
	  <RequestId>0AEDAF20-4DDF-4165-8750-47FF9C1929C9</RequestId>
</BatchStopDcdnDomainResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"0AEDAF20-4DDF-4165-8750-47FF9C1929C9"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/dcdn)查看更多错误码。

