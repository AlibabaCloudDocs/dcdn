# DescribeDcdnDomainQpsData {#doc_api_dcdn_DescribeDcdnDomainQpsData .reference}

调用DescribeDcdnDomainQpsData获取加速域名的每秒访问次数QPS。

不指定StartTime和EndTime时，默认读取过去24小时的数据，同时支持按指定的起止时间查询，两者需要同时指定。

-   支持批量域名查询，多个域名可用逗号（,）分隔。
-   最多可获取最近90天的数据。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=dcdn&api=DescribeDcdnDomainQpsData&type=RPC&version=2018-01-15)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDcdnDomainQpsData|操作接口名，系统规定参数。取值：**DescribeDcdnDomainQpsData**。

 |
|DomainName|String|否|example.com|如果参数为空，默认返回所有加速域名合并后数据。

 可输入需要查询的加速域名。支持批量域名查询，多个域名用逗号（,）分隔。

 |
|EndTime|String|否|2017-12-10T21:00:00Z|获取数据结束时间点。

 -   结束时间需大于起始时间。
-   日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ

 |
|Interval|String|否|300|查询数据的时间粒度，支持**300**、**3600**和**86400**秒。

 -   3天以内（不包含3天整）支持**300**、 **3600**、 **86400**。
-   3-31天（不包含31天整）支持**3600**和**86400**。
-   31天以上支持**86400**。

 不传和传的值不支持时，使用默认值。

 |
|IspNameEn|String|否|unicom|运营商英文名。通过**DescribeCdnRegionAndIsp**接口获得，不传为所有运营商。

 |
|LocationNameEn|String|否|beijing|区域英文名。通过**DescribeCdnRegionAndIsp**接口获得，不传为所有区域。

 |
|StartTime|String|否|2017-12-10T20:00:00Z|获取数据起始时间点。

 -   日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ。
-   最小数据粒度为1小时。
-   不写默认读取过去24小时数据。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DataInterval|String|300|每条记录的时间间隔，以秒为单位。

 |
|DomainName|String|test.com|加速域名信息。

 |
|EndTime|String|2017-12-10T21:00:00Z|结束时间。

 |
|QpsDataPerInterval| | |每个时间间隔的每秒访问次数Qps。

 |
|Acc|Float|100|总访问次数。

 |
|DynamicHttpAcc|Float|0|动态http访问次数。

 |
|DynamicHttpQps|Float|0|动态httpQPS。

 |
|DynamicHttpsAcc|Float|0|动态https访问次数。

 |
|DynamicHttpsQps|Float|0|动态httpsQPS。

 |
|Qps|Float|0.56|总QPS。

 |
|StaticHttpAcc|Float|0|静态http访问次数。

 |
|StaticHttpQps|Float|0|静态httpQPS。

 |
|StaticHttpsAcc|Float|0|静态https访问次数。

 |
|StaticHttpsQps|Float|0|静态httpsQPS。

 |
|TimeStamp|String|2017-12-10T21:00:00Z|时间片起始时刻。

 |
|RequestId|String|BEA5625F-8FCF-48F4-851B-CA63946DA664|请求ID。

 |
|StartTime|String|2017-12-10T20:00:00Z|开始时间。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://dcdn.aliyuncs.com?Action=DescribeDcdnDomainQpsData&DomainName=example.com
&StartTime=2017-12-10T20:00:00Z
&EndTime=2017-12-10T21:00:00Z
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDcdnDomainQpsDataResponse>
	  <QpsDataPerInterval>
		    <DataModule>
			      <TimeStamp>2017-12-10T21:00:00Z</TimeStamp>
			      <Qps>0.56</Qps>
			      <DynamicHttpQps>0.28</DynamicHttpQps>
			      <DynamicHttpsQps>0.28</DynamicHttpsQps>
			      <StaticHttpQps>0</StaticHttpQps>
			      <StaticHttpsQps>0</StaticHttpsQps>
			      <Acc>100</Acc>
			      <DynamicHttpAcc>50</DynamicHttpAcc>
			      <DynamicHttpsAcc>50</DynamicHttpsAcc>
			      <StaticHttpAcc>0</StaticHttpAcc>
			      <StaticHttpsAcc>0</StaticHttpsAcc>
		    </DataModule>
	  </QpsDataPerInterval>
	  <DomainName>test.com</DomainName>
	  <DataInterval>300</DataInterval>
	  <RequestId>BEA5625F-8FCF-48F4-851B-CA63946DA664</RequestId>
	  <StartTime>2017-12-10T20:00:00Z</StartTime>
	  <EndTime>2017-12-10T21:00:00Z</EndTime>
</DescribeDcdnDomainQpsDataResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"DataInterval":"300",
	"RequestId":"BEA5625F-8FCF-48F4-851B-CA63946DA664",
	"DomainName":"test.com",
	"EndTime":"2017-12-10T21:00:00Z",
	"StartTime":"2017-12-10T20:00:00Z",
	"QpsDataPerInterval":{
		"DataModule":[
			{
				"DynamicHttpQps":0.28,
				"TimeStamp":"2017-12-10T21:00:00Z",
				"StaticHttpsQps":0,
				"StaticHttpQps":0,
				"StaticHttpAcc":0,
				"Acc":100,
				"DynamicHttpsAcc":50,
				"DynamicHttpsQps":0.28,
				"DynamicHttpAcc":50,
				"Qps":0.56,
				"StaticHttpsAcc":0
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

