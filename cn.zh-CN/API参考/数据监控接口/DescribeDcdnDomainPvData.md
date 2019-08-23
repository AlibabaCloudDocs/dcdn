# DescribeDcdnDomainPvData {#doc_api_dcdn_DescribeDcdnDomainPvData .reference}

调用DescribeDcdnDomainPvData获取加速域名最小1小时粒度的PV页面访问统计。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=dcdn&api=DescribeDcdnDomainPvData&type=RPC&version=2018-01-15)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDcdnDomainPvData|操作接口名，系统规定参数。取值：**DescribeDcdnDomainPvData**。

 |
|DomainName|String|是|example.com|需要查询的加速域名，只支持一个域名，不写代表当前用户下所有域名。

 |
|EndTime|String|否|2015-11-29T00:00:00Z|获取数据结束时间点。

 -   结束时间需大于起始时间。
-   日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ

 |
|StartTime|String|否|2015-11-28T00:00:00Z|获取数据起始时间点。

 -   日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ。
-   最小数据粒度为1小时。
-   不写默认读取过去24小时数据。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DataInterval|String|3600|每条记录的时间间隔，固定值一小时或一天。

 |
|DomainName|String|example.com|加速域名信息。

 |
|EndTime|String|2015-11-29T00:00:00Z|结束时间。

 |
|PvDataInterval| | |每个时间间隔的页面访问次数。

 |
|TimeStamp|String|2015-11-28T03:00:00Z|时间片起始时刻。

 |
|Value|String|9292|详细使用数据。

 |
|RequestId|String|BCD7D917-76F1-442F-BB75-C810DE34C761|请求ID。

 |
|StartTime|String|2015-11-28T00:00:00Z|开始时间。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://dcdn.aliyuncs.com?Action=DescribeDcdnDomainPvData
&DomainName=example.com
&StartTime=2015-11-28T00:00:00Z
&EndTime=2015-11-29T00:00:00Z
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDcdnDomainPvDataResponse>
	  <DataInterval>3600</DataInterval>
	  <RequestId>BCD7D917-76F1-442F-BB75-C810DE34C761</RequestId>
	  <DomainName>example.com</DomainName>
	  <EndTime>2015-11-29T00:00:00Z</EndTime>
	  <PvDataInterval>
		    <UsageData>
			      <TimeStamp>2015-11-28T03:00:00Z</TimeStamp>
			      <Value>9292</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T23:00:00Z</TimeStamp>
			      <Value>9239</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T07:00:00Z</TimeStamp>
			      <Value>9464</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T12:00:00Z</TimeStamp>
			      <Value>9379</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T22:00:00Z</TimeStamp>
			      <Value>9243</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T10:00:00Z</TimeStamp>
			      <Value>10063</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T15:00:00Z</TimeStamp>
			      <Value>9068</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T14:00:00Z</TimeStamp>
			      <Value>9353</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T04:00:00Z</TimeStamp>
			      <Value>9513</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T02:00:00Z</TimeStamp>
			      <Value>9377</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T08:00:00Z</TimeStamp>
			      <Value>9579</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T20:00:00Z</TimeStamp>
			      <Value>9109</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T09:00:00Z</TimeStamp>
			      <Value>10631</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T06:00:00Z</TimeStamp>
			      <Value>9587</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T01:00:00Z</TimeStamp>
			      <Value>9108</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T16:00:00Z</TimeStamp>
			      <Value>9454</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T21:00:00Z</TimeStamp>
			      <Value>9285</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T19:00:00Z</TimeStamp>
			      <Value>9059</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T00:00:00Z</TimeStamp>
			      <Value>9470</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T05:00:00Z</TimeStamp>
			      <Value>11830</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T13:00:00Z</TimeStamp>
			      <Value>9992</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T17:00:00Z</TimeStamp>
			      <Value>9529</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T18:00:00Z</TimeStamp>
			      <Value>9203</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-28T11:00:00Z</TimeStamp>
			      <Value>9604</Value>
		    </UsageData>
	  </PvDataInterval>
	  <StartTime>2015-11-28T00:00:00Z</StartTime>
</DescribeDcdnDomainPvDataResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"DataInterval":"3600",
	"RequestId":"BCD7D917-76F1-442F-BB75-C810DE34C761",
	"DomainName":"example.com",
	"PvDataInterval":{
		"UsageData":[
			{
				"TimeStamp":"2015-11-28T03:00:00Z",
				"Value":"9292"
			},
			{
				"TimeStamp":"2015-11-28T23:00:00Z",
				"Value":"9239"
			},
			{
				"TimeStamp":"2015-11-28T07:00:00Z",
				"Value":"9464"
			},
			{
				"TimeStamp":"2015-11-28T12:00:00Z",
				"Value":"9379"
			},
			{
				"TimeStamp":"2015-11-28T22:00:00Z",
				"Value":"9243"
			},
			{
				"TimeStamp":"2015-11-28T10:00:00Z",
				"Value":"10063"
			},
			{
				"TimeStamp":"2015-11-28T15:00:00Z",
				"Value":"9068"
			},
			{
				"TimeStamp":"2015-11-28T14:00:00Z",
				"Value":"9353"
			},
			{
				"TimeStamp":"2015-11-28T04:00:00Z",
				"Value":"9513"
			},
			{
				"TimeStamp":"2015-11-28T02:00:00Z",
				"Value":"9377"
			},
			{
				"TimeStamp":"2015-11-28T08:00:00Z",
				"Value":"9579"
			},
			{
				"TimeStamp":"2015-11-28T20:00:00Z",
				"Value":"9109"
			},
			{
				"TimeStamp":"2015-11-28T09:00:00Z",
				"Value":"10631"
			},
			{
				"TimeStamp":"2015-11-28T06:00:00Z",
				"Value":"9587"
			},
			{
				"TimeStamp":"2015-11-28T01:00:00Z",
				"Value":"9108"
			},
			{
				"TimeStamp":"2015-11-28T16:00:00Z",
				"Value":"9454"
			},
			{
				"TimeStamp":"2015-11-28T21:00:00Z",
				"Value":"9285"
			},
			{
				"TimeStamp":"2015-11-28T19:00:00Z",
				"Value":"9059"
			},
			{
				"TimeStamp":"2015-11-28T00:00:00Z",
				"Value":"9470"
			},
			{
				"TimeStamp":"2015-11-28T05:00:00Z",
				"Value":"11830"
			},
			{
				"TimeStamp":"2015-11-28T13:00:00Z",
				"Value":"9992"
			},
			{
				"TimeStamp":"2015-11-28T17:00:00Z",
				"Value":"9529"
			},
			{
				"TimeStamp":"2015-11-28T18:00:00Z",
				"Value":"9203"
			},
			{
				"TimeStamp":"2015-11-28T11:00:00Z",
				"Value":"9604"
			}
		]
	},
	"EndTime":"2015-11-29T00:00:00Z",
	"StartTime":"2015-11-28T00:00:00Z"
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

