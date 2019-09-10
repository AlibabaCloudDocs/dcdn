# DescribeDcdnDomainRegionData {#doc_api_dcdn_DescribeDcdnDomainRegionData .reference}

调用DescribeDcdnDomainRegionData获取加速域名天粒度的用户区域分布数据统计。

不指定StartTime和EndTime时，默认读取过去24小时的数据，同时支持按指定的起止时间查询，两者需要同时指定。

 **最多可获取90天的数据。** 

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=dcdn&api=DescribeDcdnDomainRegionData&type=RPC&version=2018-01-15)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeDcdnDomainRegionData|操作接口名，系统规定参数。取值：**DescribeDcdnDomainRegionData**。

 |
|DomainName|String|否|example.com|需要查询的加速域名，只支持一个域名，不写代表所有。

 |
|EndTime|String|否|2015-12-07T12:00:00Z|结束时间需大于起始时间，北京时间。

 格式为：YYYY-MM-DDThh:mm:ssZ

 |
|StartTime|String|否|2015-12-05T12:00:00Z|获取数据起始时间点，北京时间。格式为：YYYY-MM-DDThh:mm:ssZ

 不写默认读取过去24小时数据

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DataInterval|String|300|每条记录的时间间隔，固定值1天。

 |
|DomainName|String|test.com|加速域名信息。

 |
|EndTime|String|2015-12-07T12:00:00Z|结束时间。

 |
|RequestId|String|2E5AD83F-BD7B-462E-8319-2E30E305519A|请求ID。

 |
|StartTime|String|2015-12-05T12:00:00Z|开始时间。

 |
|Value| | |各地区访问占比数据list。

 |
|AvgObjectSize|String|0|响应平均大小，单位：byte。

 |
|AvgResponseRate|String|0|平均响应速度，单位：byte/秒。

 |
|AvgResponseTime|String|0|平均响应时间，单位：毫秒。

 |
|Bps|String|0|带宽。

 |
|BytesProportion|String|0.003544181046236794|总流量占比。例如：返回90即为90%。

 |
|Proportion|String|0|访问占比数据。例如：返回90即为90% 。

 |
|Qps|String|0|每秒查询率。

 |
|Region|String|西藏自治区|地区信息。

 |
|RegionEname|String|xizang|地区英文名称。

 |
|TotalBytes|String|0|总流量。

 |
|TotalQuery|String|0|总请求次数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://dcdn.aliyuncs.com?Action=DescribeDcdnDomainRegionData
&DomainName=example.com
&StartTime=2015-12-05T12:00:00Z
&EndTime=2015-12-07T12:00:00Z
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDcdnDomainRegionDataResponse>
	  <Value>
		    <RegionProportionData>
			      <Bps>380.9614285714286</Bps>
			      <Proportion>0.01155980271270037</Proportion>
			      <TotalBytes>2400057</TotalBytes>
			      <BytesProportion>0.003544181046236794</BytesProportion>
			      <TotalQuery>3</TotalQuery>
			      <RegionEname></RegionEname>
			      <Region>日本</Region>
			      <AvgResponseRate>154.3345765545624</AvgResponseRate>
			      <AvgObjectSize>800019.0</AvgObjectSize>
			      <Qps>5.9523809523809524E-5</Qps>
			      <AvgResponseTime>5183.666666666667</AvgResponseTime>
		    </RegionProportionData>
		    <RegionProportionData>
			      <Bps>25110.431412698414</Bps>
			      <Proportion>0.31211467324291</Proportion>
			      <TotalBytes>158195717</TotalBytes>
			      <BytesProportion>0.23360872886644055</BytesProportion>
			      <TotalQuery>81</TotalQuery>
			      <RegionEname>xizang</RegionEname>
			      <Region>西藏自治区</Region>
			      <AvgResponseRate>1397.1430909315718</AvgResponseRate>
			      <AvgObjectSize>1953033.5543209878</AvgObjectSize>
			      <Qps>0.0016071428571428571</Qps>
			      <AvgResponseTime>1397.8765432098764</AvgResponseTime>
		    </RegionProportionData>
		    <RegionProportionData>
			      <Bps>40343.86242857143</Bps>
			      <Proportion>0.33908754623921084</Proportion>
			      <TotalBytes>254166333</TotalBytes>
			      <BytesProportion>0.37532921137846464</BytesProportion>
			      <TotalQuery>88</TotalQuery>
			      <RegionEname>chongqing</RegionEname>
			      <Region>重庆市</Region>
			      <AvgResponseRate>787.8073097249128</AvgResponseRate>
			      <AvgObjectSize>2888253.7875</AvgObjectSize>
			      <Qps>0.001746031746031746</Qps>
			      <AvgResponseTime>3666.193181818182</AvgResponseTime>
		    </RegionProportionData>
	  </Value>
	  <DataInterval>86400</DataInterval>
	  <RequestId>2E5AD83F-BD7B-462E-8319-2E30E305519A</RequestId>
	  <DomainName>example.com</DomainName>
	  <EndTime>2015-12-05T12:00:00Z</EndTime>
	  <StartTime>2015-12-07T12:00:00Z</StartTime>
</DescribeDcdnDomainRegionDataResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Value":{
		"RegionProportionData":[
			{
				"RegionEname":"",
				"TotalQuery":"3",
				"Region":"日本",
				"Bps":"380.9614285714286",
				"Proportion":"0.01155980271270037",
				"AvgResponseRate":"154.3345765545624",
				"AvgObjectSize":"800019.0",
				"Qps":"5.9523809523809524E-5",
				"AvgResponseTime":"5183.666666666667",
				"TotalBytes":"2400057",
				"BytesProportion":"0.003544181046236794"
			},
			{
				"RegionEname":"xizang",
				"TotalQuery":"81",
				"Region":"西藏自治区",
				"Bps":"25110.431412698414",
				"Proportion":"0.31211467324291",
				"AvgResponseRate":"1397.1430909315718",
				"AvgObjectSize":"1953033.5543209878",
				"Qps":"0.0016071428571428571",
				"AvgResponseTime":"1397.8765432098764",
				"TotalBytes":"158195717",
				"BytesProportion":"0.23360872886644055"
			},
			{
				"RegionEname":"chongqing",
				"TotalQuery":"88",
				"Region":"重庆市",
				"Bps":"40343.86242857143",
				"Proportion":"0.33908754623921084",
				"AvgResponseRate":"787.8073097249128",
				"AvgObjectSize":"2888253.7875",
				"Qps":"0.001746031746031746",
				"AvgResponseTime":"3666.193181818182",
				"TotalBytes":"254166333",
				"BytesProportion":"0.37532921137846464"
			}
		]
	},
	"DataInterval":"86400",
	"RequestId":"2E5AD83F-BD7B-462E-8319-2E30E305519A",
	"DomainName":"example.com",
	"EndTime":"2015-12-05T12:00:00Z",
	"StartTime":"2015-12-07T12:00:00Z"
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
|404|InvalidDomain.NotFound|The specified domain does not exist.|该域名不存在。|

访问[错误中心](https://error-center.aliyun.com/status/product/dcdn)查看更多错误码。

