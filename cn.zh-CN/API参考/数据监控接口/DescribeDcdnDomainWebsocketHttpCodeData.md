# DescribeDcdnDomainWebsocketHttpCodeData {#doc_api_dcdn_DescribeDcdnDomainWebsocketHttpCodeData .reference}

调用DescribeDcdnDomainWebsocketHttpCodeData获取加速域名websocket协议的最小5分钟粒度的HTTP返回码占比数据。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=dcdn&api=DescribeDcdnDomainWebsocketHttpCodeData&type=RPC&version=2018-01-15)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|DomainName|String|是|example.com|需要查询的加速域名，支持批量，多个域名用逗号（,）分隔。

 |
|Action|String|否|DescribeDcdnDomainWebsocketHttpCodeData|操作接口名，系统规定参数。取值：**DescribeDcdnDomainWebsocketHttpCodeData**。

 |
|EndTime|String|否|2018-03-01T06:00:00Z|结束时间需大于起始时间。

 获日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ

 |
|Interval|String|否|300|查询数据的时间粒度，支持**300**、**3600**和**86400**秒。

 -   3天以内（不包含3天整）支持**300**、**3600**、**86400**。
-   3-31天（不包含31天整）支持**3600**和**86400**。
-   31天以上支持**86400**。

 不传和传的值不支持时，使用默认值。

 |
|IspNameEn|String|否|unicom|运营商英文名，通过**DescribeCdnRegionAndIsp**接口获得，不传为所有运营商。

 |
|LocationNameEn|String|否|beijing|区域英文名，通过**DescribeCdnRegionAndIsp**接口获得，不传为所有区域。

 |
|StartTime|String|否|2018-03-01T05:00:00Z|获取数据起始时间点。

 -   日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ。
-   最小数据粒度为5分钟。

 不写默认读取过去24小时数据

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DataInterval|String|3600|每条记录的时间间隔，以秒为单位，固定值300S。

 |
|DataPerInterval| | |每个时间间隔的HTTP返回码占比数据。

 |
|TimeStamp|String|2018-03-01T11:00:00|时间片起始时刻。

 |
|WebsocketHttpCodeDataPerInterval| | |各返回码占比使用数据list。

 |
|Code|Integer|9|http返回码。

 |
|Count|Float|50|总数。

 |
|Proportion|Float|43|占比使用数据。

 |
|DomainName|String|example.com|加速域名信息。

 |
|EndTime|String|2018-03-01T13:00:00Z|结束时间。

 |
|RequestId|String|91FC2D9D-B042-4634-8A5C-7B8E7482C22D|请求ID。

 |
|StartTime|String|2018-03-01T05:00:00Z|开始时间。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://dcdn.aliyuncs.com?Action=DescribeDcdnDomainWebsocketHttpCodeData
&DomainName="example.com,example1.com"
&StartTime=2018-03-01T05:00:00Z
&EndTime=2018-03-01T13:00:00Z
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDcdnDomainWebsocketHttpCodeDataResponse>
	  <DataInterval>3600</DataInterval>
	  <RequestId>91FC2D9D-B042-4634-8A5C-7B8E7482C22D</RequestId>
	  <EndTime>2018-03-01T13:00:00Z</EndTime>
	  <StartTime>2018-03-01T05:00:00Z</StartTime>
	  <HttpCodeDataPerInterval>
		    <DataModule>
			      <TimeStamp>2018-03-01T13:00:00Z</TimeStamp>
			      <WebsocketHttpCode></WebsocketHttpCode>
		    </DataModule>
		    <DataModule>
			      <TimeStamp>2018-03-01T12:00:00Z</TimeStamp>
			      <WebsocketHttpCode>
				        <HttpCodeDataModule>
					          <Count>16</Count>
					          <Proportion>100</Proportion>
					          <Code>404</Code>
				        </HttpCodeDataModule>
			      </WebsocketHttpCode>
		    </DataModule>
		    <DataModule>
			      <TimeStamp>2018-03-01T11:00:00Z</TimeStamp>
			      <WebsocketHttpCode>
				        <HttpCodeDataModule>
					          <Count>9</Count>
					          <Proportion>50</Proportion>
					          <Code>403</Code>
				        </HttpCodeDataModule>
				        <HttpCodeDataModule>
					          <Count>9</Count>
					          <Proportion>50</Proportion>
					          <Code>504</Code>
				        </HttpCodeDataModule>
			      </WebsocketHttpCode>
		    </DataModule>
	  </HttpCodeDataPerInterval>
</DescribeDcdnDomainWebsocketHttpCodeDataResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"DataInterval":3600,
	"RequestId":"91FC2D9D-B042-4634-8A5C-7B8E7482C22D",
	"EndTime":"2018-03-01T13:00:00Z",
	"StartTime":"2018-03-01T05:00:00Z",
	"HttpCodeDataPerInterval":{
		"DataModule":[
			{
				"TimeStamp":"2018-03-01T13:00:00Z",
				"WebsocketHttpCode":{
					"HttpCodeDataModule":[]
				}
			},
			{
				"TimeStamp":"2018-03-01T12:00:00Z",
				"WebsocketHttpCode":{
					"HttpCodeDataModule":[
						{
							"Count":16,
							"Proportion":100,
							"Code":404
						}
					]
				}
			},
			{
				"TimeStamp":"2018-03-01T11:00:00Z",
				"WebsocketHttpCode":{
					"HttpCodeDataModule":[
						{
							"Count":9,
							"Proportion":50,
							"Code":403
						},
						{
							"Count":9,
							"Proportion":50,
							"Code":504
						}
					]
				}
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

