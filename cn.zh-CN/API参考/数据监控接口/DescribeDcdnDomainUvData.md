# DescribeDcdnDomainUvData {#doc_api_dcdn_DescribeDcdnDomainUvData .reference}

调用DescribeDcdnDomainUvData获取加速域名最小1小时粒度的UV页面独立访问统计。

 **调用该接口前，请您注意：** 

-   不指定StartTime和EndTime时，默认读取过去24小时的数据，同时支持按指定的起止时间查询，两者需要同时指定。
-   只支持一个域名，或当前用户下所有域名。
-   最多可获取最近90天的数据。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=dcdn&api=DescribeDcdnDomainUvData&type=RPC&version=2018-01-15)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDcdnDomainUvData|操作接口名，系统规定参数，取值：**DescribeDcdnDomainUvData**。

 |
|DomainName|String|是|example.com|需要查询的加速域名，只支持一个域名，不写代表当前用户下所有域名。

 |
|EndTime|String|否|2015-11-30T00:00:00Z|获取数据结束时间点。

 -   结束时间需大于起始时间。
-   日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ

 |
|StartTime|String|否|2015-11-29T00:00:00Z|获取数据起始时间点。

 -   日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ。
-   最小数据粒度为1小时。
-   不写默认读取过去24小时数据。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DataInterval|String|3600|每条记录的时间间隔，以秒为单位，固定值1小时。

 |
|DomainName|String|example.com|加速域名信息。

 |
|EndTime|String|2015-11-30T00:00:00Z|结束时间。

 |
|RequestId|String|E9D3257A-1B7C-414C-90C1-8D07AC47BCAC|请求ID。

 |
|StartTime|String|2015-11-29T00:00:00Z|开始时间。

 |
|UvDataInterval| | |每个时间间隔的页面独立访问次数。

 |
|TimeStamp|String|2015-11-29T00:00:00Z|时间片起始时刻。

 |
|Value|String|326|详细使用数据。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://dcdn.aliyuncs.com?Action=DescribeDcdnDomainUvData
&DomainName=example.com
&StartTime=2015-11-29T00:00:00Z
&EndTime=2015-11-30T00:00:00Z
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDcdnDomainUvDataResponse>
	  <DataInterval>3600</DataInterval>
	  <RequestId>E9D3257A-1B7C-414C-90C1-8D07AC47BCAC</RequestId>
	  <DomainName>example.com</DomainName>
	  <EndTime>2015-11-30T00:00:00Z</EndTime>
	  <StartTime>2015-11-29T00:00:00Z</StartTime>
	  <UvDataInterval>
		    <UsageData>
			      <TimeStamp>2015-11-29T20:00:00Z</TimeStamp>
			      <Value>318</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-29T18:00:00Z</TimeStamp>
			      <Value>318</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-29T03:00:00Z</TimeStamp>
			      <Value>329</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-29T21:00:00Z</TimeStamp>
			      <Value>316</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-29T07:00:00Z</TimeStamp>
			      <Value>319</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-29T00:00:00Z</TimeStamp>
			      <Value>326</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-29T11:00:00Z</TimeStamp>
			      <Value>321</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-29T10:00:00Z</TimeStamp>
			      <Value>313</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-29T08:00:00Z</TimeStamp>
			      <Value>331</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-29T01:00:00Z</TimeStamp>
			      <Value>324</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-29T04:00:00Z</TimeStamp>
			      <Value>330</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-29T14:00:00Z</TimeStamp>
			      <Value>335</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-29T12:00:00Z</TimeStamp>
			      <Value>318</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-29T23:00:00Z</TimeStamp>
			      <Value>310</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-29T17:00:00Z</TimeStamp>
			      <Value>309</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-29T22:00:00Z</TimeStamp>
			      <Value>320</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-29T16:00:00Z</TimeStamp>
			      <Value>309</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-29T02:00:00Z</TimeStamp>
			      <Value>317</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-29T06:00:00Z</TimeStamp>
			      <Value>309</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-29T19:00:00Z</TimeStamp>
			      <Value>308</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-29T13:00:00Z</TimeStamp>
			      <Value>347</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-29T15:00:00Z</TimeStamp>
			      <Value>341</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-29T05:00:00Z</TimeStamp>
			      <Value>347</Value>
		    </UsageData>
		    <UsageData>
			      <TimeStamp>2015-11-29T09:00:00Z</TimeStamp>
			      <Value>312</Value>
		    </UsageData>
	  </UvDataInterval>
</DescribeDcdnDomainUvDataResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"DataInterval":"3600",
	"RequestId":"E9D3257A-1B7C-414C-90C1-8D07AC47BCAC",
	"DomainName":"example.com",
	"EndTime":"2015-11-30T00:00:00Z",
	"StartTime":"2015-11-29T00:00:00Z",
	"UvDataInterval":{
		"UsageData":[
			{
				"TimeStamp":"2015-11-29T20:00:00Z",
				"Value":"318"
			},
			{
				"TimeStamp":"2015-11-29T18:00:00Z",
				"Value":"318"
			},
			{
				"TimeStamp":"2015-11-29T03:00:00Z",
				"Value":"329"
			},
			{
				"TimeStamp":"2015-11-29T21:00:00Z",
				"Value":"316"
			},
			{
				"TimeStamp":"2015-11-29T07:00:00Z",
				"Value":"319"
			},
			{
				"TimeStamp":"2015-11-29T00:00:00Z",
				"Value":"326"
			},
			{
				"TimeStamp":"2015-11-29T11:00:00Z",
				"Value":"321"
			},
			{
				"TimeStamp":"2015-11-29T10:00:00Z",
				"Value":"313"
			},
			{
				"TimeStamp":"2015-11-29T08:00:00Z",
				"Value":"331"
			},
			{
				"TimeStamp":"2015-11-29T01:00:00Z",
				"Value":"324"
			},
			{
				"TimeStamp":"2015-11-29T04:00:00Z",
				"Value":"330"
			},
			{
				"TimeStamp":"2015-11-29T14:00:00Z",
				"Value":"335"
			},
			{
				"TimeStamp":"2015-11-29T12:00:00Z",
				"Value":"318"
			},
			{
				"TimeStamp":"2015-11-29T23:00:00Z",
				"Value":"310"
			},
			{
				"TimeStamp":"2015-11-29T17:00:00Z",
				"Value":"309"
			},
			{
				"TimeStamp":"2015-11-29T22:00:00Z",
				"Value":"320"
			},
			{
				"TimeStamp":"2015-11-29T16:00:00Z",
				"Value":"309"
			},
			{
				"TimeStamp":"2015-11-29T02:00:00Z",
				"Value":"317"
			},
			{
				"TimeStamp":"2015-11-29T06:00:00Z",
				"Value":"309"
			},
			{
				"TimeStamp":"2015-11-29T19:00:00Z",
				"Value":"308"
			},
			{
				"TimeStamp":"2015-11-29T13:00:00Z",
				"Value":"347"
			},
			{
				"TimeStamp":"2015-11-29T15:00:00Z",
				"Value":"341"
			},
			{
				"TimeStamp":"2015-11-29T05:00:00Z",
				"Value":"347"
			},
			{
				"TimeStamp":"2015-11-29T09:00:00Z",
				"Value":"312"
			}
		]
	}
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

