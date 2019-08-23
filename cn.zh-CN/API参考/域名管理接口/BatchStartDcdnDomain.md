# BatchStartDcdnDomain {#doc_api_dcdn_BatchStartDcdnDomain .reference}

调用BatchStartDcdnDomain启用状态为“”停用“”的加速域名，将DomainStatus变更为online。

域名对应账户如果由于欠费或域名处于非法状态，您将无法正常调用该接口启用加速域名。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=dcdn&api=BatchStartDcdnDomain&type=RPC&version=2018-01-15)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|BatchStartDcdnDomain|操作接口名。系统规定参数。取值：**BatchStartDcdnDomain**。

 |
|DomainNames|String|是|test.com|需要接入全站加速的域名，用逗号（,）分隔。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|0AEDAF20-4DDF-4165-8750-47FF9C1929C9|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://dcdn.aliyuncs.com?Action=BatchStartDcdnDomain
&DomainNames=test.com
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<BatchStartDcdnDomainResponse>
	  <RequestId>0AEDAF20-4DDF-4165-8750-47FF9C1929C9</RequestId>
</BatchStartDcdnDomainResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"0AEDAF20-4DDF-4165-8750-47FF9C1929C9"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/dcdn)查看更多错误码。

