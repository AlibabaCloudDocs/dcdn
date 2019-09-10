# DescribeDcdnDomainHitRateData {#doc_api_dcdn_DescribeDcdnDomainHitRateData .reference}

调用DescribeDcdnDomainHitRateData获取加速域名的命中率。

 **调用该接口前，请您注意：** 

-   不指定StartTime和EndTime时，默认读取过去24小时的数据；同时支持按指定的起止时间查询，两者需要同时指定。
-   支持批量域名查询，多个域名可用逗号（,）分隔。
-   最多可获取最近90天的数据。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=dcdn&api=DescribeDcdnDomainHitRateData&type=RPC&version=2018-01-15)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeDcdnDomainHitRateData|操作接口名，系统规定参数。取值：**DescribeDcdnDomainHitRateData**。

 |
|DomainName|String|否|example.com|需要查询的加速域名。只支持一个域名，不写代表该用户所有域名。

 |
|EndTime|String|否|2018-03-02T15:00:00Z|获取数据结束时间点。

 -   结束时间需大于起始时间。
-   获日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ。

 |
|Interval|String|否|300|查询数据的时间粒度，支持**300**、 **3600**和**86400**秒。

 -   3天以内（不包含3天整）支持**300**、 **3600**、 **86400**。
-   3-31天（不包含31天整）支持**3600**和**86400**。
-   31天以上支持**86400**。

 不传和传的值不支持时，使用默认值。

 |
|StartTime|String|否|2018-03-02T12:00:00Z|获取数据起始时间点。

 -   日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ。
-   最小数据粒度为5分钟。
-   不写默认读取过去24小时数据。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DataInterval|String|3600|每条记录的时间间隔，以秒为单位。

 |
|DomainName|String|example.com|加速域名信息。

 |
|EndTime|String|2018-03-02T15:00:00Z|结束时间。

 |
|HitRatePerInterval| | |每个时间间隔的命中百分占比。

 |
|ByteHitRate|Float|0|字节命中百分占比。

 |
|ReqHitRate|Float|0|请求命中百分占比。

 |
|TimeStamp|String|2018-03-02T13:00:00Z|时间片起始时刻。

 |
|RequestId|String|4D07ABFE-4737-4834-B1B9-A661308C47B4|请求ID。

 |
|StartTime|String|2018-03-02T12:00:00Z|开始时间。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://scdn.aliyuncs.com?Action=DescribeDcdnDomainHitRateData
&DomainName=example.com
&StartTime=2018-03-02T12:00:00Z
&EndTime=2018-03-02T15:00:00Z
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDcdnDomainHitRateDataResponse>
	  <DomainName>test.com</DomainName>
	  <DataInterval>3600</DataInterval>
	  <HitRatePerInterval>
		    <DataModule>
			      <ByteHitRate>0</ByteHitRate>
			      <TimeStamp>2018-03-02T15:00:00Z</TimeStamp>
			      <ReqHitRate>0</ReqHitRate>
		    </DataModule>
		    <DataModule>
			      <ByteHitRate>0</ByteHitRate>
			      <TimeStamp>2018-03-02T14:00:00Z</TimeStamp>
			      <ReqHitRate>0</ReqHitRate>
		    </DataModule>
		    <DataModule>
			      <ByteHitRate>0</ByteHitRate>
			      <TimeStamp>2018-03-02T13:00:00Z</TimeStamp>
			      <ReqHitRate>0</ReqHitRate>
		    </DataModule>
		    <DataModule>
			      <ByteHitRate>0</ByteHitRate>
			      <TimeStamp>2018-03-02T12:00:00Z</TimeStamp>
			      <ReqHitRate>0</ReqHitRate>
		    </DataModule>
	  </HitRatePerInterval>
	  <RequestId>4D07ABFE-4737-4834-B1B9-A661308C47B4</RequestId>
	  <EndTime>2018-03-02T15:00:00Z</EndTime>
	  <StartTime>2018-03-02T12:00:00Z</StartTime>
</DescribeDcdnDomainHitRateDataResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"DataInterval":3600,
	"HitRatePerInterval":{
		"DataModule":[
			{
				"TimeStamp":"2018-03-02T15:00:00Z",
				"ByteHitRate":0,
				"ReqHitRate":0
			},
			{
				"TimeStamp":"2018-03-02T14:00:00Z",
				"ByteHitRate":0,
				"ReqHitRate":0
			},
			{
				"TimeStamp":"2018-03-02T13:00:00Z",
				"ByteHitRate":0,
				"ReqHitRate":0
			},
			{
				"TimeStamp":"2018-03-02T12:00:00Z",
				"ByteHitRate":0,
				"ReqHitRate":0
			}
		]
	},
	"RequestId":"4D07ABFE-4737-4834-B1B9-A661308C47B4",
	"DomainName":"test.com",
	"EndTime":"2018-03-02T15:00:00Z",
	"StartTime":"2018-03-02T12:00:00Z"
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

