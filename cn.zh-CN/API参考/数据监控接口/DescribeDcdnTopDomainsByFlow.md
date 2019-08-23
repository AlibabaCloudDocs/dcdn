# DescribeDcdnTopDomainsByFlow {#doc_api_dcdn_DescribeDcdnTopDomainsByFlow .reference}

调用DescribeDcdnTopDomainsByFlow获取用户按流量排名的域名。

不指定StartTime和EndTime时，默认读取当月的数据，同时支持按指定的起止时间查询，两者需要同时指定。

最多可获取90天的数据。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=dcdn&api=DescribeDcdnTopDomainsByFlow&type=RPC&version=2018-01-15)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDcdnTopDomainsByFlow|操作接口名，系统规定参数。取值：**DescribeDcdnTopDomainsByFlow**。

 |
|EndTime|String|否|2016-03-14T07:34:00Z|获取数据结束时间点。

 -   结束时间需大于起始时间。
-   日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ。

 |
|Limit|Long|否|20|域名获取数量限制，默认为**20**，取值支持**1**~**100**。

 |
|StartTime|String|否|2016-03-01T04:00:00Z|获取数据起始时间点。

 -   日期格式按照ISO8601表示法，并使用UTC时间。格式为：YYYY-MM-DDThh:mm:ssZ。
-   最小数据粒度为5分钟。
-   不写默认读取当月数据。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DomainCount|Long|68|账户下域名总数。

 |
|DomainOnlineCount|Long|68|账户下**正在运行**域名总数。

 |
|EndTime|String|2016-03-14T07:34:00Z|结束时间。

 |
|RequestId|String|4E09C5D7-E1CF-4CAA-A45E-8727F4C8FD70|请求ID。

 |
|StartTime|String|2016-03-14T06:34:00Z|开始时间。

 |
|TopDomains| | |排名域名列表。

 |
|DomainName|String|example.com|域名。

 |
|MaxBps|Long|22139626|带宽峰值。

 |
|MaxBpsTime|String|2018-11-01T08:10:00Z|带宽峰值时刻，使用 ISO8601 表示法，并使用UTC时间。

 格式为：YYYY-MM-DDThh:mm:ssZ。

 |
|Rank|Long|1|排名。

 |
|TotalAccess|Long|3|访问次数。

 |
|TotalTraffic|String|123|总流量。

 |
|TrafficPercent|String|21.686305274906182|流量占比。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://dcdn.aliyuncs.com?Action=DescribeDcdnTopDomainsByFlow
&StartTime=2016-03-01T04:00:00Z
&EndTime=2016-03-14T07:34:00Z
&Limit=5
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDcdnTopDomainsByFlowResponse>
	  <DomainCount>68</DomainCount>
	  <DomainOnlineCount>68</DomainOnlineCount>
	  <RequestId>4E09C5D7-E1CF-4CAA-A45E-8727F4C8FD70</RequestId>
	  <EndTime>2016-03-14T07:34:00Z</EndTime>
	  <TopDomains>
		    <TopDomain>
			      <MaxBps>22139626</MaxBps>
			      <Rank>1</Rank>
			      <TrafficPercent>30.64191989360235</TrafficPercent>
			      <TotalTraffic>2043859876683.9001</TotalTraffic>
			      <TotalAccess>107784230</TotalAccess>
			      <DomainName>example.com</DomainName>
			      <MaxBpsTime>2018-11-01T08:10:00Z</MaxBpsTime>
		    </TopDomain>
		    <TopDomain>
			      <MaxBps>1008772351</MaxBps>
			      <Rank>2</Rank>
			      <TrafficPercent>25.936032624725815</TrafficPercent>
			      <TotalTraffic>1729970466149.2002</TotalTraffic>
			      <TotalAccess>3843128</TotalAccess>
			      <DomainName>example.com</DomainName>
			      <MaxBpsTime>2018-11-01T08:10:00Z</MaxBpsTime>
		    </TopDomain>
		    <TopDomain>
			      <MaxBps>16046911</MaxBps>
			      <Rank>3</Rank>
			      <TrafficPercent>21.686305274906182</TrafficPercent>
			      <TotalTraffic>1446507574551.6</TotalTraffic>
			      <TotalAccess>547567</TotalAccess>
			      <DomainName>example.com</DomainName>
			      <MaxBpsTime>2018-11-01T08:10:00Z</MaxBpsTime>
		    </TopDomain>
		    <TopDomain>
			      <MaxBps>15990893</MaxBps>
			      <Rank>4</Rank>
			      <TrafficPercent>21.261081185428147</TrafficPercent>
			      <TotalTraffic>1418144519687.5</TotalTraffic>
			      <TotalAccess>548380</TotalAccess>
			      <DomainName>example.com</DomainName>
			      <MaxBpsTime>2018-11-01T08:10:00Z</MaxBpsTime>
		    </TopDomain>
		    <TopDomain>
			      <MaxBps>473599</MaxBps>
			      <Rank>5</Rank>
			      <TrafficPercent>0.4308743788055894</TrafficPercent>
			      <TotalTraffic>28739937242.500004</TotalTraffic>
			      <TotalAccess>152150</TotalAccess>
			      <DomainName>ali.ddimg.cn</DomainName>
			      <MaxBpsTime>2018-11-01T08:10:00Z</MaxBpsTime>
		    </TopDomain>
	  </TopDomains>
	  <StartTime>2016-03-01T04:00:00Z</StartTime>
</DescribeDcdnTopDomainsByFlowResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"DomainCount":68,
	"DomainOnlineCount":68,
	"RequestId":"4E09C5D7-E1CF-4CAA-A45E-8727F4C8FD70",
	"TopDomains":{
		"TopDomain":[
			{
				"Rank":1,
				"MaxBps":22139626,
				"TotalTraffic":2043859876683.9001,
				"TrafficPercent":30.64191989360235,
				"TotalAccess":107784230,
				"DomainName":"example.com",
				"MaxBpsTime":"2018-11-01T08:10:00Z"
			},
			{
				"Rank":2,
				"MaxBps":1008772351,
				"TotalTraffic":1729970466149.2002,
				"TrafficPercent":25.936032624725815,
				"TotalAccess":3843128,
				"DomainName":"example.com",
				"MaxBpsTime":"2018-11-01T08:10:00Z"
			},
			{
				"Rank":3,
				"MaxBps":16046911,
				"TotalTraffic":1446507574551.6,
				"TrafficPercent":21.686305274906182,
				"TotalAccess":547567,
				"DomainName":"example.com",
				"MaxBpsTime":"2018-11-01T08:10:00Z"
			},
			{
				"Rank":4,
				"MaxBps":15990893,
				"TotalTraffic":1418144519687.5,
				"TrafficPercent":21.261081185428147,
				"TotalAccess":548380,
				"DomainName":"example.com",
				"MaxBpsTime":"2018-11-01T08:10:00Z"
			},
			{
				"Rank":5,
				"MaxBps":473599,
				"TotalTraffic":28739937242.500004,
				"TrafficPercent":0.4308743788055894,
				"TotalAccess":152150,
				"DomainName":"ali.ddimg.cn",
				"MaxBpsTime":"2018-11-01T08:10:00Z"
			}
		]
	},
	"EndTime":"2016-03-14T07:34:00Z",
	"StartTime":"2016-03-01T04:00:00Z"
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

