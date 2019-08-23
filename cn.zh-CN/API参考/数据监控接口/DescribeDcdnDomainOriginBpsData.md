# DescribeDcdnDomainOriginBpsData {#doc_api_dcdn_DescribeDcdnDomainOriginBpsData .reference}

调用DescribeDcdnDomainOriginBpsData获取加速域名的回源带宽监控数据。

获取数据单位：bit/second。

-   不指定StartTime和EndTime时，默认读取过去24小时的数据；同时支持按指定的起止时间查询，两者需要同时指定。
-   支持批量域名查询，多个域名用逗号（,）分隔。
-   最多可获取最近90天的数据。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=dcdn&api=DescribeDcdnDomainOriginBpsData&type=RPC&version=2018-01-15)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDcdnDomainOriginBpsData|操作接口名，系统规定参数。取值：**DescribeDcdnDomainOriginBpsData**。

 |
|DomainName|String|否|example.com|如果参数为空，默认返回所有加速域名合并后数据。

 可输入需要查询的加速域名。支持批量域名查询，多个域名用逗号（,）分隔。

 |
|EndTime|String|否|2017-12-10T21:00:00Z|获取数据结束时间点。

 -   结束时间需大于起始时间。
-   获日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ。

 |
|Interval|String|否|300|查询数据的时间粒度，支持**300**、 **3600**和**86400**秒。

 -   3天以内（不包含3天整）支持**300**、 **3600**、 **86400**。
-   3-31天（不包含31天整）支持**3600**和**86400**。
-   31天以上支持**86400**。

 不传和传的值不支持时，使用默认值。

 |
|StartTime|String|否|2017-12-10T20:00:00Z|获取数据起始时间点。

 -   日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ。
-   最小数据粒度为5分钟。
-   不写默认读取过去24小时数据。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DataInterval|String|300|每条记录的时间间隔，以秒为单位。

 |
|DomainName|String|example.com|加速域名信息。

 |
|EndTime|String|2017-12-10T21:00:00Z|结束时间。

 |
|OriginBpsDataPerInterval| | |每个时间间隔的回源带宽数据。

 |
|DynamicHttpOriginBps|Float|100|动态http回源带宽数据。

 |
|DynamicHttpsOriginBps|Float|100|动态https回源带宽数据。

 |
|OriginBps|Float|100|回源带宽数据。

 |
|StaticHttpOriginBps|Float|100|静态http回源带宽数据。

 |
|StaticHttpsOriginBps|Float|100|静态https回源带宽数据。

 |
|TimeStamp|String|2017-12-10T21:00:00Z|时间片起始时刻。

 |
|RequestId|String|7CBCD6AD-B016-42E5-AE0B-B3731DE8F755|请求ID。

 |
|StartTime|String|2017-12-10T20:00:00Z|开始时间。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://dcdn.aliyuncs.com?Action=DescribeDcdnDomainOriginBpsData
&DomainName=example.com
&StartTime=2017-12-10T20:00:00Z
&EndTime=2017-12-10T21:00:00Z
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDcdnDomainOriginBpsDataResponse>
	  <DomainName>test.com</DomainName>
	  <DataInterval>300</DataInterval>
	  <SrcBpsDataPerInterval>
		    <DataModule>
			      <TimeStamp>2017-12-10T21:00:00Z</TimeStamp>
			      <OriginBps>200</OriginBps>
			      <DynamicHttpOriginBps>100</DynamicHttpOriginBps>
			      <DynamicHttpsOriginBps>100</DynamicHttpsOriginBps>
			      <StaticHttpOriginBps>0</StaticHttpOriginBps>
			      <StaticHttpsOriginBps>0</StaticHttpsOriginBps>
		    </DataModule>
	  </SrcBpsDataPerInterval>
	  <RequestId>7CBCD6AD-B016-42E5-AE0B-B3731DE8F755</RequestId>
	  <StartTime>2017-12-10T20:00:00Z</StartTime>
	  <EndTime>2017-12-10T21:00:00Z</EndTime>
</DescribeDcdnDomainOriginBpsDataResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"SrcBpsDataPerInterval":{
		"DataModule":[
			{
				"DynamicHttpOriginBps":100,
				"TimeStamp":"2017-12-10T21:00:00Z",
				"OriginBps":200,
				"StaticHttpOriginBps":0,
				"StaticHttpsOriginBps":0,
				"DynamicHttpsOriginBps":100
			}
		]
	},
	"DataInterval":"300",
	"RequestId":"7CBCD6AD-B016-42E5-AE0B-B3731DE8F755",
	"DomainName":"test.com",
	"EndTime":"2017-12-10T21:00:00Z",
	"StartTime":"2017-12-10T20:00:00Z"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|MissingTimeParameter|The StartTime and EndTime must be both specified.|请同时提供开始时间和结束时间。|
|400|InvalidStartTime.Malformed|The specified StartTime is invalid.|请提供正确的开始时间格式。日期格式按照ISO8601表示法，并使用UTC时间。\\n格式为：YYYY-MM-DDThh:mm:ssZ|
|400|InvalidEndTime.Malformed|The specified EndTime is invalid.|请提供正确的结束时间格式。日期格式按照ISO8601表示法，并使用UTC时间。 格式为：YYYY-MM-DDThh:mm:ssZ|
|400|InvalidEndTime.Mismatch|The specified EndTime is earlier than the StartTime.|结束时间早于开始时间，请检查。|
|400|InvalidStartTime.ValueNotSupported|The specified StartTime is invalid.|不支持该开始时间，请重新填写。|

访问[错误中心](https://error-center.aliyun.com/status/product/dcdn)查看更多错误码。

