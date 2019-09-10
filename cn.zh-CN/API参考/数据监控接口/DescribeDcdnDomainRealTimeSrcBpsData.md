# DescribeDcdnDomainRealTimeSrcBpsData {#doc_api_dcdn_DescribeDcdnDomainRealTimeSrcBpsData .reference}

调用DescribeDcdnDomainRealTimeSrcBpsData获取域名一分钟粒度回源带宽数据。

 **调用该接口前，请您注意：** 

-   单次查询StartTime和EndTime跨度不能超过24小时。
-   如果StartTime和EndTime均未指定，默认返回当前时间起一小时内的数据。
-   支持批量域名查询，多个域名用逗号（,）分隔。
-   最多可获取最近7天的数据。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=dcdn&api=DescribeDcdnDomainRealTimeSrcBpsData&type=RPC&version=2018-01-15)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDcdnDomainRealTimeSrcBpsData|操作接口名，系统规定参数。取值：**DescribeDcdnDomainRealTimeSrcBpsData**。

 |
|DomainName|String|是|example.com|需要查询的加速域名。支持批量域名查询，多个域名用逗号（,）分隔。

 |
|EndTime|String|否|2015-12-10T20:01:00Z|获取数据结束时间点。

 -   结束时间需大于起始时间。
-   获日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ。

 |
|StartTime|String|否|2015-12-10T20:00:00Z|获取数据起始时间点。

 -   日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ。
-   不写默认读取过去1小时数据。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DataInterval|String|300|每条记录的时间间隔，以秒为单位。

 |
|DomainName|String|example.com|加速域名信息。

 |
|EndTime|String|2015-12-10T20:01:00Z|结束时间。

 |
|RealTimeSrcBpsDataPerInterval| | |每个时间间隔的回源带宽数据。

 |
|TimeStamp|String|2015-12-10T20:01:00Z|时间片起始时刻。

 |
|Value|String|0|详细使用数据。

 |
|RequestId|String|7CBCD6AD-B016-42E5-AE0B-B3731DE8F755|请求ID。

 |
|StartTime|String|2015-12-10T20:00:00Z|开始时间。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://dcdn.aliyuncs.com?Action=DescribeDcdnDomainRealTimeSrcBpsData
&DomainName=example.com
&StartTime=2015-12-10T20:00:00Z
&EndTime=2015-12-10T20:01:00Z
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDcdnDomainRealTimeSrcBpsDataResponse>
	  <DomainName>example.com</DomainName>
	  <DataInterval>60</DataInterval>
	  <RealTimeSrcBpsDataPerInterval>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:00:00Z</TimeStamp>
			      <Value>821</Value>
		    </DataModule>
		    <DataModule>
			      <TimeStamp>2015-12-10T20:01:00Z</TimeStamp>
			      <Value>0</Value>
		    </DataModule>
	  </RealTimeSrcBpsDataPerInterval>
	  <RequestId>7CBCD6AD-B016-42E5-AE0B-B3731DE8F755</RequestId>
	  <StartTime>2015-12-10T20:00:00Z</StartTime>
	  <EndTime>2015-12-10T20:01:00Z</EndTime>
</DescribeDcdnDomainRealTimeSrcBpsDataResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RealTimeSrcBpsDataPerInterval":{
		"DataModule":[
			{
				"TimeStamp":"2015-12-10T20:00:00Z",
				"Value":"821"
			},
			{
				"TimeStamp":"2015-12-10T20:01:00Z",
				"Value":"0"
			}
		]
	},
	"DataInterval":"60",
	"RequestId":"7CBCD6AD-B016-42E5-AE0B-B3731DE8F755",
	"DomainName":"example.com",
	"EndTime":"2015-12-10T20:01:00Z",
	"StartTime":"2015-12-10T20:00:00Z"
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

