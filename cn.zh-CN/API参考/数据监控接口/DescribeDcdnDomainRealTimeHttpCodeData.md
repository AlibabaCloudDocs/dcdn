# DescribeDcdnDomainRealTimeHttpCodeData {#doc_api_dcdn_DescribeDcdnDomainRealTimeHttpCodeData .reference}

调用DescribeDcdnDomainRealTimeHttpCodeData获取加速域名1分钟粒度的HTTP返回码占比数据。

 **调用该接口前，请您注意：** 

-   单次查询StartTime和EndTime跨度不能超过24小时。
-   如果StartTime和EndTime均未指定，默认返回当前时间起一小时内的数据。
-   支持批量域名查询，多个域名用逗号（,）分隔。
-   最多可获取最近7天的数据。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=dcdn&api=DescribeDcdnDomainRealTimeHttpCodeData&type=RPC&version=2018-01-15)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDcdnDomainRealTimeHttpCodeData|操作接口名，系统规定参数。取值：**DescribeDcdnDomainRealTimeHttpCodeData**。

 |
|DomainName|String|是|example.com|如果参数为空，默认返回所有加速域名合并后数据。

 可输入需要查询的加速域名。支持批量域名查询，多个域名用逗号（,）分隔。

 |
|EndTime|String|否|2017-12-10T21:00:00Z|获取数据结束时间点。

 -   结束时间需大于起始时间。
-   获日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ。

 |
|IspNameEn|String|否|beijing|运营商英文名，通过**DescribeCdnRegionAndIsp**接口获得，不传为所有运营商。

 |
|LocationNameEn|String|否|unicom|区域英文名，通过**DescribeCdnRegionAndIsp**接口获得，不传为所有区域。

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
|RealTimeHttpCodeData| | |各返回码占比使用数据list。

 |
|TimeStamp|String|2017-12-10T20:00:00Z|时间片起始时刻。

 |
|Value| | |返回码信息。

 |
|Code|String|11111|http返回码。

 |
|Count|String|1|数量。

 |
|Proportion|String|0.01155980271270037|占比使用数据。

 |
|RequestId|String|B955107D-E658-4E77-B913-E0AC3D31693E|请求ID。

 |
|StartTime|String|2017-12-10T20:00:00Z|开始时间。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://dcdn.aliyuncs.com?Action=DescribeDcdnDomainRealTimeHttpCodeData
&DomainName=example.com
&StartTime=2017-12-10T20:00:00Z
&EndTime=2017-12-10T21:00:00Z
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDcdnDomainRealTimeHttpCodeDataResponse>
	  <DomainName>example.com</DomainName>
	  <DataInterval>300</DataInterval>
	  <RealTimeHttpCodeData>
		    <TimeStamp>2017-12-10T20:00:00Z</TimeStamp>
		    <RealTimeCodeProportionData>
			      <Code>111111</Code>
			      <Proportion>0.01155980271270037</Proportion>
			      <Count>1</Count>
		    </RealTimeCodeProportionData>
	  </RealTimeHttpCodeData>
	  <RequestId>B955107D-E658-4E77-B913-E0AC3D31693E</RequestId>
	  <StartTime>2017-12-10T20:00:00Z</StartTime>
	  <EndTime>2017-12-10T21:00:00Z</EndTime>
</DescribeDcdnDomainRealTimeHttpCodeDataResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"DataInterval":"300",
	"RequestId":"B955107D-E658-4E77-B913-E0AC3D31693E",
	"DomainName":"example.com",
	"EndTime":"2017-12-10T21:00:00Z",
	"StartTime":"2017-12-10T20:00:00Z",
	"RealTimeHttpCodeData":{
		"TimeStamp":"2017-12-10T20:00:00Z",
		"RealTimeCodeProportionData":[
			{
				"Count":"1",
				"Proportion":"0.01155980271270037",
				"Code":"111111"
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

