# DescribeDcdnIpaService {#doc_api_dcdn_DescribeDcdnIpaService .reference}

调用DescribeDcdnIpaService查询全站加速ipa服务状态。包括：当前计费类型，服务开通时间，下次生效的计费类型，当前业务状态等。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=dcdn&api=DescribeDcdnIpaService&type=RPC&version=2018-01-15)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDcdnIpaService|操作接口名，系统规定参数，取值：**DescribeDcdnIpaService**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|ChangingAffectTime|String|2018-03-31T16:00:00Z|GMT时间，变配生效时间，需要与当前时间比较，晚于当前时间才能在前端页面显示。

 |
|ChangingChargeType|String|PayByBandwidth|下次生效的计费类型：

 -   **PayByTraffic**：流量。
-   **PayByBandwidth**：带宽。
-   **PayByBandwidth95**：月95。
-   **PayByBandwidth\_monthavg**：月平均带宽。
-   **PayByBandwidth\_month4th**：月第四峰值。
-   **PayByBandwidth\_monthday95avg**：月平均95。
-   **PayByBandwidth\_nighthalf95**：月95夜间减半。

 |
|InstanceId|String|1883927335936173|实例ID。

 |
|InternetChargeType|String|PayByBandwidth|计费类型：

 -   **PayByTraffic**：流量。
-   **PayByBandwidth**：带宽。
-   **PayByBandwidth95**：月95。
-   **PayByBandwidth\_monthavg**：月平均带宽。
-   **PayByBandwidth\_month4th**：月第四峰值。
-   **PayByBandwidth\_monthday95avg**：月平均95。
-   **PayByBandwidth\_nighthalf95**：月95夜间减半。

 |
|OpeningTime|String|2018-03-19T11:16:11Z|开通服务时间，ISO 8601时间格式。

 |
|OperationLocks| | |业务锁定状态。

 |
|LockReason|String|financial|锁定原因。例如：**financial**（欠费）。

 |
|RequestId|String|EF2AEBC2-EDBD-41CF-BF64-7E095D42D6EF|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
https://dcdn.aliyuncs.com?&Action=DescribeDcdnIpaService
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDcdnIpaServiceResponse>
	  <ChangingChargeType>PayByBandwidth</ChangingChargeType>
	  <OpeningTime>2018-03-19T11:16:11Z</OpeningTime>
	  <InstanceId>1883927335936173</InstanceId>
	  <RequestId>EF2AEBC2-EDBD-41CF-BF64-7E095D42D6EF</RequestId>
	  <ChangingAffectTime>2018-03-31T16:00:00Z</ChangingAffectTime>
	  <OperationLocks>
		    <LockReason>
			      <LockReason>financial</LockReason>
		    </LockReason>
	  </OperationLocks>
	  <InternetChargeType>PayByTraffic</InternetChargeType>
</DescribeDcdnIpaServiceResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"OpeningTime":"2018-03-19T11:16:11Z",
	"ChangingChargeType":"PayByBandwidth",
	"RequestId":"EF2AEBC2-EDBD-41CF-BF64-7E095D42D6EF",
	"InstanceId":"1883927335936173",
	"ChangingAffectTime":"2018-03-31T16:00:00Z",
	"OperationLocks":{
		"LockReason":[
			{
				"LockReason":"financial"
			}
		]
	},
	"InternetChargeType":"PayByTraffic"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|DcdnIpaServiceNotFound|The DCDN IPA service has not been activated.|没有开通Dcdn Ipa服务。|

访问[错误中心](https://error-center.aliyun.com/status/product/dcdn)查看更多错误码。

