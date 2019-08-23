# DescribeUserDcdnIpaStatus {#doc_api_dcdn_DescribeUserDcdnIpaStatus .reference}

调用DescribeUserDcdnIpaStatus查询全站加速IPA是否开通，是否欠费。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=dcdn&api=DescribeUserDcdnIpaStatus&type=RPC&version=2018-01-15)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeUserDcdnIpaStatus|操作接口名，系统规定参数，取值：**DescribeUserDcdnIpaStatus**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Enabled|Boolean|true|是否已开通IPA服务。

 |
|InDebt|Boolean|false|是否欠费。

 |
|InDebtOverdue|Boolean|false|是否欠费超期。

 |
|OnService|Boolean|true|服务是否可用（不欠费）。

 |
|RequestId|String|4F51E9C3-728F-4E35-952D-0ED87A06A8A1|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
https://dcdn.aliyuncs.com?&Action=DescribeUserDcdnIpaStatus
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeUserDcdnIpaStatusResponse>
	  <Enabled>true</Enabled>
	  <InDebtOverdue>false</InDebtOverdue>
	  <InDebt>false</InDebt>
	  <OnService>true</OnService>
	  <RequestId>4F51E9C3-728F-4E35-952D-0ED87A06A8A1</RequestId>
</DescribeUserDcdnIpaStatusResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Enabled":true,
	"OnService":true,
	"InDebt":false,
	"InDebtOverdue":false,
	"RequestId":"4F51E9C3-728F-4E35-952D-0ED87A06A8A1"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/dcdn)查看更多错误码。

