# DescribeDcdnDomainRealTimeByteHitRateData {#doc_api_dcdn_DescribeDcdnDomainRealTimeByteHitRateData .reference}

调用DescribeDcdnDomainRealTimeByteHitRateData获取域名1分钟粒度字节命中率数据。

 **调用该接口前，请您注意：** 

-   可以查询7天内的数据，单次查询StartTime和EndTime跨度不能超过24小时。
-   指定StartTime，未指定EndTime的情况：默认查询从指定的StartTime起一小时内的数据。
-   指定EndTime，未指定SdtartTime的情况：默认查询从指定的EndTime起向前推一个小时内的数据。
-   由于存在多域名合并存储的情况，可能会导致命中率数据不准确，具体情况以配置为准。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=dcdn&api=DescribeDcdnDomainRealTimeByteHitRateData&type=RPC&version=2018-01-15)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDcdnDomainRealTimeByteHitRateData|操作接口名，系统规定参数，取值：**DescribeDcdnDomainRealTimeByteHitRateData**。

 |
|DomainName|String|是|example.com|域名。多个之间用逗号（,）隔开。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Data| | |字节命中率数据list。

 |
|ByteHitRate|Float|0.8956940476262277|请求命中率数据。

 |
|TimeStamp|String|2016-10-20T04:00:00Z|数据时间戳，日期格式按照ISO8601表示法，并使用UTC时间。例如：2016-10-20T04:00:00Z。

 |
|RequestId|String|B955107D-E658-4E77-B913-E0AC3D31693E|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://dcdn.aliyuncs.com?Action=DescribeDcdnDomainRealTimeByteHitRateData
&DomainName=example.com
&StartTime=2017-12-10T20:00:00Z
&EndTime=2017-12-10T21:00:00Z
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDcdnDomainRealTimeByteHitRateDataResponse>
	  <Data>
		    <ReqHitRate>0.8956940476262277</ReqHitRate>
		    <TimeStamp>2016-10-20T04:00:00Z</TimeStamp>
	  </Data>
	  <RequestId>B955107D-E658-4E77-B913-E0AC3D31693E</RequestId>
</DescribeDcdnDomainRealTimeByteHitRateDataResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Data":[
		{
			"TimeStamp":"2016-10-20T04:00:00Z",
			"ReqHitRate":"0.8956940476262277"
		}
	],
	"RequestId":"B955107D-E658-4E77-B913-E0AC3D31693E"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/dcdn)查看更多错误码。

