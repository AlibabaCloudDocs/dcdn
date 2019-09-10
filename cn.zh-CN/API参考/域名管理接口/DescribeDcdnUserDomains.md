# DescribeDcdnUserDomains {#doc_api_dcdn_DescribeDcdnUserDomains .reference}

调用DescribeDcdnUserDomains查询用户名下所有的全站加速域名。支持域名模糊匹配过滤和域名状态过滤。

域名状态包括：

-   运行中（表示域名服务状态正常）。
-   已停止。
-   配置中。
-   配置失败。
-   审核中。
-   审核失败。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=dcdn&api=DescribeDcdnUserDomains&type=RPC&version=2018-01-15)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDcdnUserDomains|操作接口名。系统规定参数，取值：**DescribeDcdnUserDomains**。

 |
|CheckDomainShow|Boolean|否|false|检查domain是否展出。

 |
|DomainName|String|否|example.com|域名模糊匹配过滤。

 |
|DomainSearchType|String|否|fuzzy\_match|域名查询类型。默认值：**fuzzy\_match**。取值范围：

 -   **fuzzy\_match**：模糊匹配。
-   **pre\_match**：前匹配。
-   **suf\_match**：后匹配。
-   **full\_match**：完全匹配。

 |
|DomainStatus|String|否|运行中|域名状态过滤。

 |
|FuncFilter|String|否|config|过滤。支持**config**（已开通**funcid**）和**unconfig**（未开通**funcid**）。

 |
|FuncId|String|否|图片鉴黄|功能ID。

 |
|PageNumber|Integer|否|1|页数。取值范围：**1**~**100000**。

 |
|PageSize|Integer|否|20|分页大小。默认**20**，最大**50**，取值：**1**~**50**之前的任意整数。

 |
|ResourceGroupId|String|否|123|资源组ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Domains| | |由PageData组成的数组格式，返回加速域名的状态信息。

 |
|Cname|String|test.aliyun.com.w.alikunlun.com|加速域名对应的CNAME域名。

 |
|Description|String|audit failed|审核失败原因。

 |
|DomainStatus|String|online|加速域名状态。取值范围：

 -   **online**：启用。
-   **offline**：停用。
-   **configuring**：配置中。

 -   **configure\_failed**：配置失败。
-   **checking**：正在审核。
-   **check\_failed**：审核失败。

 |
|GmtCreated|String|2015-10-28T11:05:50Z|加速域名创建时间。

 |
|GmtModified|String|2015-10-28T09:31:59Z|加速域名修改时间。

 |
|ResourceGroupId|String|abcd1234abcd1234|资源组ID。

 |
|SSLProtocol|String|on|HTTPS开关。取值范围：

 -   **on**：已开启。
-   **off**：未开启。

 |
|Sandbox|String|normal|沙箱。

 |
|Sources| | |源站信息。

 |
|Content|String|example.cpm|源站地址。

 |
|Port|Integer|80|源站端口。

 |
|Priority|String|20|优先级。

 |
|Type|String|oss|源站类型。

 |
|Weight|String|20|权重。

 |
|PageNumber|Long|1|返回数据的页码。

 |
|PageSize|Long|12|整页大小。

 |
|RequestId|String|AA75AADB-5E25-4970-B480-EAA1F5658483|请求ID。

 |
|TotalCount|Long|12|总条数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
https://dcdn.aliyuncs.com&Action=DescribeDcdnUserDomains
&PageNumber=1
&PageSize=5
&DomainSearchType=fuzzy_match
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDcdnUserDomainsResponse>
	  <PageNumber>1</PageNumber>
	  <TotalCount>16</TotalCount>
	  <PageSize>5</PageSize>
	  <RequestId>AA75AADB-5E25-4970-B480-EAA1F5658483</RequestId>
	  <Domains>
		    <PageData>
			      <DomainStatus>configure_failed</DomainStatus>
			      <DomainName>www.example.com</DomainName>
			      <GmtModified>2015-10-28T11:05:52Z</GmtModified>
			      <GmtCreated>2015-10-28T09:32:51Z</GmtCreated>
			      <Description>audit failed</Description>
			      <ResourceGroupId>abcd1234abcd1234</ResourceGroupId>
		    </PageData>
		    <PageData>
			      <DomainStatus>configure_failed</DomainStatus>
			      <DomainName>www.example.com</DomainName>
			      <GmtModified>2015-10-28T11:05:50Z</GmtModified>
			      <GmtCreated>2015-10-28T09:31:59Z</GmtCreated>
			      <ResourceGroupId>abcd1234abcd1234</ResourceGroupId>
		    </PageData>
		    <PageData>
			      <Cname>onlytest.cdnpe.com.w.alikunlun.net</Cname>
			      <DomainStatus>online</DomainStatus>
			      <DomainName>www.example.com</DomainName>
			      <GmtModified>2015-10-27T06:26:34Z</GmtModified>
			      <GmtCreated>2015-10-23T09:30:00Z</GmtCreated>
			      <ResourceGroupId>abcd1234abcd1234</ResourceGroupId>
		    </PageData>
		    <PageData>
			      <Cname>test11.cdnpe.com.w.kunlunAr.com</Cname>
			      <DomainStatus>online</DomainStatus>
			      <DomainName>www.example.com</DomainName>
			      <GmtModified>2015-10-23T09:23:29Z</GmtModified>
			      <GmtCreated>2015-10-23T09:23:20Z</GmtCreated>
			      <ResourceGroupId>abcd1234abcd1234</ResourceGroupId>
		    </PageData>
		    <PageData>
			      <Cname>test.aliyun.com.w.alikunlun.com</Cname>
			      <DomainStatus>online</DomainStatus>
			      <DomainName>www.example.com</DomainName>
			      <GmtModified>2015-10-23T09:02:11Z</GmtModified>
			      <GmtCreated>2015-10-23T09:01:57Z</GmtCreated>
			      <ResourceGroupId>abcd1234abcd1234</ResourceGroupId>
		    </PageData>
	  </Domains>
</DescribeDcdnUserDomainsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"TotalCount":16,
	"PageSize":5,
	"RequestId":"AA75AADB-5E25-4970-B480-EAA1F5658483",
	"Domains":{
		"PageData":[
			{
				"Description":"audit failed",
				"ResourceGroupId":"abcd1234abcd1234",
				"DomainStatus":"configure_failed",
				"DomainName":"www.example.com",
				"GmtModified":"2015-10-28T11:05:52Z",
				"GmtCreated":"2015-10-28T09:32:51Z"
			},
			{
				"ResourceGroupId":"abcd1234abcd1234",
				"DomainStatus":"configure_failed",
				"DomainName":"www.example.com",
				"GmtModified":"2015-10-28T11:05:50Z",
				"GmtCreated":"2015-10-28T09:31:59Z"
			},
			{
				"Cname":"onlytest.cdnpe.com.w.alikunlun.net",
				"ResourceGroupId":"abcd1234abcd1234",
				"DomainStatus":"online",
				"DomainName":"www.example.com",
				"GmtModified":"2015-10-27T06:26:34Z",
				"GmtCreated":"2015-10-23T09:30:00Z"
			},
			{
				"Cname":"test11.cdnpe.com.w.kunlunAr.com",
				"ResourceGroupId":"abcd1234abcd1234",
				"DomainStatus":"online",
				"DomainName":"www.example.com",
				"GmtModified":"2015-10-23T09:23:29Z",
				"GmtCreated":"2015-10-23T09:23:20Z"
			},
			{
				"Cname":"test.aliyun.com.w.alikunlun.com",
				"ResourceGroupId":"abcd1234abcd1234",
				"DomainStatus":"online",
				"DomainName":"www.example.com",
				"GmtModified":"2015-10-23T09:02:11Z",
				"GmtCreated":"2015-10-23T09:01:57Z"
			}
		]
	}
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidPageNumber.ValueNotSupported|The specified value of PageNumber is not supported.|页码参数错误，请重新填写。|
|400|InvalidPageSize.ValueNotSupported|The specified value of PageSize is invalid.|PageSize参数错误，请重新填写。|
|400|InvalidDomainStatus.ValueNotSupported|The specified value of DomainStatus is invalid.|DomainStatus值错误，请重新填写。|
|400|InvalidDomainName.Malformed|The specified DomainName is invalid.|域名格式错误。|
|400|InvalidDomainSearchType.ValueNotSupported|The specified value of DomainSearchType is invalid.|DomainSearchType值错误，请重新填写。|

访问[错误中心](https://error-center.aliyun.com/status/product/dcdn)查看更多错误码。

