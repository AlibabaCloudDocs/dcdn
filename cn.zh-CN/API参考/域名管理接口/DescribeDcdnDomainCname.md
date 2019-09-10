# DescribeDcdnDomainCname {#doc_api_dcdn_DescribeDcdnDomainCname .reference}

调用DescribeDcdnDomainCname检测用户是否完成Cname，支持多个域名。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=dcdn&api=DescribeDcdnDomainCname&type=RPC&version=2018-01-15)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|DomainName|String|是|example.com|需要接入CDN的域名，多个域名以逗号（,）分隔。

 |
|Action|String|否|DescribeDcdnDomainCname|操作接口名，系统规定参数。取值：**DescribeDcdnDomainCname**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|CnameDatas| | |Cname信息。

 |
|Cname|String|xxx.com|Cname。

 |
|Domain|String|.example.com|域名。

 |
|Status|Integer|6|状态。

 |
|RequestId|String|15C66C7B-671A-4297-9187-2C4477247A74|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://dcdn.aliyuncs.com?Action=DescribeDcdnDomainCname
&DomainName=example.com,example1.com
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDcdnDomainCnameResponse>
	  <RequestId>15C66C7B-671A-4297-9187-2C4477247A74</RequestId>
	  <CnameDatas>
		    <Domain>.example.com</Domain>
		    <Cname>xxx</Cname>
		    <Status>6</Status>
	  </CnameDatas>
</DescribeDcdnDomainCnameResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"15C66C7B-671A-4297-9187-2C4477247A74",
	"CnameDatas":[
		{
			"Cname":"xxx",
			"Status":"6",
			"Domain":".example.com"
		}
	]
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/dcdn)查看更多错误码。

