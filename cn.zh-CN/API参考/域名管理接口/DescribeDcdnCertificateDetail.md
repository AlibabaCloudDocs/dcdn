# DescribeDcdnCertificateDetail {#doc_api_dcdn_DescribeDcdnCertificateDetail .reference}

调用DescribeDcdnCertificateDetail获取证书详细信息。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=dcdn&api=DescribeDcdnCertificateDetail&type=RPC&version=2018-01-15)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDcdnCertificateDetail|操作接口名。系统规定参数。取值：**DescribeDcdnCertificateDetail**。

 |
|CertName|String|是|yourCertName|证书名称。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Cert|String|-----BEGIN CERTIFICATE-----xxx-----END CERTIFICATE-----|证书内容。

 |
|CertId|Long|123|证书ID。

 |
|CertName|String|123|证书名称。

 |
|Key|String|null|—

 |
|RequestId|String|C7C69682-7F88-40DD-A198-10D0309E439B|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://dcdn.aliyuncs.com??Action=DescribeDcdnCertificateDetail
&CertName=xxx
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDcdnCertificateDetailResponse>
	  <CertId>xxx</CertId>
	  <RequestId>C7C69682-7F88-40DD-A198-10D0309E439B</RequestId>
	  <CertName>证书名称</CertName>
	  <Cert>-----BEGIN CERTIFICATE-----xxx-----END CERTIFICATE-----</Cert>
</DescribeDcdnCertificateDetailResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"CertId":"123",
	"RequestId":"C7C69682-7F88-40DD-A198-10D0309E439B",
	"CertName":"证书名称",
	"Cert":"-----BEGIN CERTIFICATE-----xxx-----END CERTIFICATE-----"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/dcdn)查看更多错误码。

