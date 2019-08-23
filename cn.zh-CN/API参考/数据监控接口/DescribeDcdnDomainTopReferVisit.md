# DescribeDcdnDomainTopReferVisit {#doc_api_dcdn_DescribeDcdnDomainTopReferVisit .reference}

调用DescribeDcdnDomainTopReferVisit获取加速域名某天的热门页面引用次数排名。

不指定StartTime时，默认读取过去1天的数据。

只支持一个域名。最多可获取最近90天的数据。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=dcdn&api=DescribeDcdnDomainTopReferVisit&type=RPC&version=2018-01-15)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDcdnDomainTopReferVisit|操作接口名，系统规定参数。取值：**DescribeDcdnDomainTopReferVisit**。

 |
|DomainName|String|是|example.com|加速域名信息，只支持一个域名。

 |
|SortBy|String|否|pv|排序方式，支持**traf**和**pv**，默认**pv**。

 |
|StartTime|String|否|2018-10-03T16:00:00Z|开始获取数据的时间点。不写默认读取过去24小时数据。

 格式为：YYYY-MM-DDThh:mm:ssZ。查询某天的数据，建议传YYYY-MM-DDT16:00:00Z

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DomainName|String|example.com|加速域名信息。

 |
|RequestId|String|95994621-8382-464B-8762-C708E73568D1|请求ID。

 |
|StartTime|String|2018-10-03T16:00:00Z|查询指定日期。

 |
|TopReferList| | |全部热门ReferUrllist。

 |
|Flow|String|460486880|流量。单位：byte。

 |
|FlowProportion|Float|0.35|流量占比。

 |
|ReferDetail|String|123.57.158.x|完整的ReferUrl地址。

 |
|VisitData|String|229567|访问次数。

 |
|VisitProportion|Float|0.35|访问占比。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://dcdn.aliyuncs.com?Action=DescribeDcdnDomainTopReferVisit&DomainName=example.com
&StartTime=2018-10-03T16:00:00Z
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDcdnDomainTopReferVisitResponse>
	  <TopReferList>
		    <ReferList>
			      <VisitData>229567</VisitData>
			      <ReferDetail>-</ReferDetail>
			      <VisitProportion>0.35</VisitProportion>
			      <Flow>460486880</Flow>
			      <FlowProportion>0.35</FlowProportion>
		    </ReferList>
		    <ReferList>
			      <VisitData>2496</VisitData>
			      <ReferDetail>123.57.158.x</ReferDetail>
			      <VisitProportion>0.35</VisitProportion>
			      <Flow>460486880</Flow>
			      <FlowProportion>0.35</FlowProportion>
		    </ReferList>
		    <ReferList>
			      <VisitData>448</VisitData>
			      <ReferDetail>live-hunantv.cdnpe.com</ReferDetail>
			      <VisitProportion>0.35</VisitProportion>
			      <Flow>460486880</Flow>
			      <FlowProportion>0.35</FlowProportion>
		    </ReferList>
		    <ReferList>
			      <VisitData>3</VisitData>
			      <ReferDetail>video.ccdemo.ccgslb.net</ReferDetail>
			      <VisitProportion>0.35</VisitProportion>
			      <Flow>460486880</Flow>
			      <FlowProportion>0.35</FlowProportion>
		    </ReferList>
	  </TopReferList>
	  <RequestId>95994621-8382-464B-8762-C708E73568D1</RequestId>
	  <DomainName>example.com</DomainName>
	  <StartTime>2018-10-03T16:00:00Z</StartTime>
</DescribeDcdnDomainTopReferVisitResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"TopReferList":{
		"ReferList":[
			{
				"Flow":"460486880",
				"VisitProportion":0.35,
				"VisitData":"229567",
				"ReferDetail":"-",
				"FlowProportion":0.35
			},
			{
				"Flow":"460486880",
				"VisitProportion":0.35,
				"VisitData":"2496",
				"ReferDetail":"123.57.158.8",
				"FlowProportion":0.35
			},
			{
				"Flow":"460486880",
				"VisitProportion":0.35,
				"VisitData":"448",
				"ReferDetail":"live-hunantv.cdnpe.com",
				"FlowProportion":0.35
			},
			{
				"Flow":"460486880",
				"VisitProportion":0.35,
				"VisitData":"3",
				"ReferDetail":"video.ccdemo.ccgslb.net",
				"FlowProportion":0.35
			}
		]
	},
	"RequestId":"95994621-8382-464B-8762-C708E73568D1",
	"DomainName":"example.com",
	"StartTime":"2018-10-03T16:00:00Z"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidStartTime.Malformed|The specified StartTime is invalid.|请提供正确的开始时间格式。日期格式按照ISO8601表示法，并使用UTC时间。\\n格式为：YYYY-MM-DDThh:mm:ssZ|
|400|InvalidStartTime.ValueNotSupported|The specified StartTime is invalid.|不支持该开始时间，请重新填写。|

访问[错误中心](https://error-center.aliyun.com/status/product/dcdn)查看更多错误码。

