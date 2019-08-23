# DescribeDcdnDomainRealTimeQpsData {#doc_api_dcdn_DescribeDcdnDomainRealTimeQpsData .reference}

调用DescribeDcdnDomainRealTimeQpsData获取域名1分钟粒度每秒访问次数数据。

 **调用该接口前，请您注意：** 

-   可以查询7天内的数据，单次查询StartTime和EndTime跨度不能超过24小时。
-   指定StartTime，未指定EndTime的情况：默认查询从指定的StartTime起一小时内的数据。
-   指定EndTime，未指定SdtartTime的情况：默认查询从指定的EndTime起向前推一个小时内的数据。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=dcdn&api=DescribeDcdnDomainRealTimeQpsData&type=RPC&version=2018-01-15)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDcdnDomainRealTimeQpsData|操作接口名，系统规定参数，取值：DescribeDcdnDomainRealTimeQpsData。

 |
|DomainName|String|是|example.com|域名。多个之间用逗号（,）隔开。

 |
|EndTime|String|否|2018-01-02T11:27:00Z|结束时间，日期格式按照ISO8601表示法，并使用UTC时间,例如：2016-10-20T04:00:00Z。

 |
|IspNameEn|String|否|telecom|运营商英文名，通过**DescribeCdnRegionAndIsp**接口获得，不传为所有运营商。

 |
|LocationNameEn|String|否|beijing|区域英文名，通过**DescribeCdnRegionAndIsp**接口获得，不传为所有区域。

 |
|StartTime|String|否|2018-01-02T11:26:00Z|起始时间，日期格式按照ISO8601表示法，并使用UTC时间,例如：2016-10-20T04:00:00Z。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Data| | |数据list。

 |
|Qps|Float|1851.25|qps数据。

 |
|TimeStamp|String|2018-01-02T11:26:00Z|数据时间戳，日期格式按照ISO8601表示法，并使用UTC时间。例如：2016-10-20T04:00:00Z。

 |
|RequestId|String|32DC9806-E9F9-4490-BBDC-B3A9E32FCC1D|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
https://dcdn.aliyuncs.com/?Action=DescribeDcdnDomainRealTimeQpsData
&DomainName=example.com
&EndTime=2018-01-02T11:26:00Z
&IspNameEn=telecom
&LocationNameEn=beijing
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDcdnDomainRealTimeQpsDataResponse>
	  <Data>
		    <QpsModel>
			      <TimeStamp>2018-01-02T11:26:00Z</TimeStamp>
			      <Qps>1851.25</Qps>
		    </QpsModel>
		    <QpsModel>
			      <TimeStamp>2018-01-02T11:25:00Z</TimeStamp>
			      <Qps>8967.7</Qps>
		    </QpsModel>
	  </Data>
	  <RequestId>32DC9806-E9F9-4490-BBDC-B3A9E32FCC1D</RequestId>
</DescribeDcdnDomainRealTimeQpsDataResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Data":{
		"QpsModel":[
			{
				"TimeStamp":"2018-01-02T11:26:00Z",
				"Qps":1851.25
			},
			{
				"TimeStamp":"2018-01-02T11:25:00Z",
				"Qps":8967.7
			}
		]
	},
	"RequestId":"32DC9806-E9F9-4490-BBDC-B3A9E32FCC1D"
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

