# DescribeDcdnDomainLog {#doc_api_dcdn_DescribeDcdnDomainLog .reference}

调用DescribeDcdnDomainLog获取指定域名的原始访问日志的下载地址。

不指定StartTime和EndTime时，默认读取过去24小时的日志数据。

StartTime和EndTime同时指定，按指定的起止时间查询日志。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=dcdn&api=DescribeDcdnDomainLog&type=RPC&version=2018-01-15)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDcdnDomainLog|操作接口名，系统规定参数。取值：**DescribeDcdnDomainLog**。

 |
|DomainName|String|是|example.com|域名（只支持单个查询）。

 |
|EndTime|String|否|2017-01-01T12:12:20Z|结束时间需大于起始时间。起止时间和结束时间，间隔不超过一年。

 获取日期格式按照ISO8601表示法，并使用UTC时间。

 |
|PageNumber|Long|否|2|取得第几页。

 取值范围：大于**1**的任意整数。

 |
|PageSize|Long|否|300|分页大小。默认值：**300**。最大值：**1000**。

 取值：**1**~**1000**之前的任意整数。

 |
|StartTime|String|否|2017-01-01T12:12:20Z|获取日志起始时间点。

 日期格式按照ISO8601表示法，并使用UTC时间。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DomainLogDetails| | |DomainLogDetail组成的数据。

 |
|LogCount|Long|12|本页返回的总条数。

 |
|LogInfos| | |LogInfoDetail组成的数据。

 |
|EndTime|String|1521979200|结束时间。

 |
|LogName|String|example1.com\_2018\_03\_25\_190000\_200000.gz|日志名称。

 |
|LogPath|String|cdnlog2.aliyuncs.com/test1.example.com/2018\_03\_25/example1.com\_2018\_03\_25\_190000\_200000.gz?xxx|日志路径。

 |
|LogSize|Long|2645401|日志大小。

 |
|StartTime|String|1521975600|开始时间。

 |
|PageInfos| | |PageInfoDetail组成的数据。

 |
|PageIndex|Long|2|返回数据的页码。

 |
|PageSize|Long|10|整页大小。

 |
|Total|Long|20|总条数。

 |
|DomainName|String|test1.example.com|域名。

 |
|RequestId|String|077D0284-F041-4A41-A932-B48377FDAA25|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://dcdn.aliyuncs.com?Action=DescribeDcdnDomainLog
&DomainName=example.com
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDcdnDomainLogResponse>
	  <RequestId>077D0284-F041-4A41-A932-B48377FDAA25</RequestId>
	  <DomainLogDetails>
		    <DomainLogDetail>
			      <LogInfos>
				        <LogInfoDetail>
					          <LogName>example1.com_2018_03_25_180000_190000.gz</LogName>
					          <LogPath>cdnlog2.aliyuncs.com/test1.example.com/2018_03_25/example1.com_2018_03_25_180000_190000.gz?xxx</LogPath>
					          <EndTime>1521975600</EndTime>
					          <StartTime>1521972000</StartTime>
					          <LogSize>2645401</LogSize>
				        </LogInfoDetail>
				        <LogInfoDetail>
					          <LogName>example1.com_2018_03_25_190000_200000.gz</LogName>
					          <LogPath>cdnlog2.aliyuncs.com/test1.example.com/2018_03_25/example1.com_2018_03_25_190000_200000.gz?xxx</LogPath>
					          <EndTime>1521979200</EndTime>
					          <StartTime>1521975600</StartTime>
					          <LogSize>2653965</LogSize>
				        </LogInfoDetail>
			      </LogInfos>
			      <LogCount>20</LogCount>
			      <PageInfos>
				        <PageIndex>1</PageIndex>
				        <PageSize>20</PageSize>
				        <Total>20</Total>
			      </PageInfos>
			      <DomainName>test1.example.com</DomainName>
		    </DomainLogDetail>
	  </DomainLogDetails>
</DescribeDcdnDomainLogResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"077D0284-F041-4A41-A932-B48377FDAA25",
	"DomainLogDetails":{
		"DomainLogDetail":[
			{
				"LogInfos":{
					"LogInfoDetail":[
						{
							"LogName":"example1.com_2018_03_25_180000_190000.gz",
							"LogPath":"cdnlog2.aliyuncs.com/test1.example.com/2018_03_25/example1.com_2018_03_25_180000_190000.gz?xxx",
							"EndTime":"1521975600",
							"LogSize":2645401,
							"StartTime":"1521972000"
						},
						{
							"LogName":"example1.com_2018_03_25_190000_200000.gz",
							"LogPath":"cdnlog2.aliyuncs.com/test1.example.com/2018_03_25/example1.com_2018_03_25_190000_200000.gz?xxx",
							"EndTime":"1521979200",
							"LogSize":2653965,
							"StartTime":"1521975600"
						}
					]
				},
				"LogCount":20,
				"PageInfos":{
					"PageSize":20,
					"PageIndex":1,
					"Total":20
				},
				"DomainName":"test1.example.com"
			}
		]
	}
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidEndTime.Mismatch|The specified EndTime is earlier than the StartTime.|结束时间早于开始时间，请检查。|

访问[错误中心](https://error-center.aliyun.com/status/product/dcdn)查看更多错误码。

