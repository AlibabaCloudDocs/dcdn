# DescribeDcdnCertificateList {#doc_api_dcdn_DescribeDcdnCertificateList .reference}

调用DescribeDcdnCertificateList获取证书列表信息。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=dcdn&api=DescribeDcdnCertificateList&type=RPC&version=2018-01-15)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDcdnCertificateList|操作接口名，系统规定参数。取值：**DescribeDcdnCertificateList**。

 |
|DomainName|String|否|example.com|加速域名。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|CertificateListModel| | |CertificateListModel类型。

 |
|CertList| | |证书列表信息。

 |
|CertId|Long|123|证书ID。

 |
|CertName|String|证书2|证书名称。

 |
|Common|String|test|证书中的CN属性，一般是一个域名。

 |
|Fingerprint|String|xxx|证书指纹。

 |
|Issuer|String|xxx|证书发行商。

 |
|LastTime|Long|1512388659|时间戳。

 |
|Count|Integer|123|证书个数。

 |
|RequestId|String|FC0E34AC-0239-44A7-AB0E-800DE522C8DA|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://dcdn.aliyuncs.com?Action=DescribeDcdnCertificateList
&DomainName=xxx
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDcdnCertificateListResponse>
	  <CertificateListModel>
		    <Count>2</Count>
		    <CertList>
			      <Cert>
				        <CertName>证书1</CertName>
				        <Issuer>xxx</Issuer>
				        <LastTime>1512388610</LastTime>
				        <CertId>xxx</CertId>
				        <Common>test</Common>
				        <Fingerprint>xxx</Fingerprint>
			      </Cert>
			      <Cert>
				        <CertName>证书2</CertName>
				        <Issuer>xxx</Issuer>
				        <LastTime>1512388659</LastTime>
				        <CertId>xxx</CertId>
				        <Common>test</Common>
				        <Fingerprint>xxx</Fingerprint>
			      </Cert>
		    </CertList>
	  </CertificateListModel>
	  <RequestId>FC0E34AC-0239-44A7-AB0E-800DE522C8DA</RequestId>
</DescribeDcdnCertificateListResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"CertificateListModel":{
		"Count":2,
		"CertList":{
			"Cert":[
				{
					"CertId":"xxx",
					"Issuer":"xxx",
					"LastTime":1512388610,
					"CertName":"证书1",
					"Common":"test",
					"Fingerprint":"xxx"
				},
				{
					"CertId":"xxx",
					"Issuer":"xxx",
					"LastTime":1512388659,
					"CertName":"证书2",
					"Common":"test",
					"Fingerprint":"xxx"
				}
			]
		}
	},
	"RequestId":"FC0E34AC-0239-44A7-AB0E-800DE522C8DA"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/dcdn)查看更多错误码。

