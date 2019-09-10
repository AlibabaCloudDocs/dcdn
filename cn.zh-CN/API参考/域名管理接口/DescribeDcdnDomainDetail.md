# DescribeDcdnDomainDetail {#doc_api_dcdn_DescribeDcdnDomainDetail .reference}

调用DescribeDcdnDomainDetail获取指定加速域名配置的基本信息。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=dcdn&api=DescribeDcdnDomainDetail&type=RPC&version=2018-01-15)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDcdnDomainDetail|操作接口名，系统规定参数。取值：**DescribeDcdnDomainDetail**。

 |
|DomainName|String|是|example.com|接入加速的域名。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DomainDetail| | |域名信息列表。

 |
|CertName|String|证书名称|如果开启HTTPS，此处为证书名称。

 |
|Cname|String|bb.test.com.dcdn7mhp.com|为加速域名生成的一个CNAME域名，需要在域名解析服务商处将加速域名CNAME解析到该域名。

 |
|Description|String|audit failed|审核失败原因。

 |
|DomainName|String|bb.test.com|加速的域名。

 |
|DomainStatus|String|online|加速域名运行状态。 取值范围：

 -   **online**：启用。
-   **offline**：停用。
-   **configuring**：配置中。
-   **configure\_failed**：配置失败。
-   **checking**：正在审核。
-   **check\_failed**：审核失败。

 |
|GmtCreated|String|2017-11-27T06:51:26Z|创建时间。

 |
|GmtModified|String|2017-11-27T06:51:25Z|最近修改时间。

 |
|ResourceGroupId|String|123|资源组ID。

 |
|SSLProtocol|String|on|是否开启SSL证书。取值范围：

 -   on：**开启**。
-   off：**关闭**。

 |
|SSLPub|String|xxx|如果开启HTTPS，此处为证书公钥。

 |
|Scope|String|overseas|区域。

 |
|Sources| | |源站信息。

 |
|Content|String|oss.com|回源地址。

 |
|Enabled|String|online|状态。

 |
|Port|Integer|80|端口。支持443和80。

 |
|Priority|String|50|优先级。

 |
|Type|String|oss|源站类型。取值范围：

 -   ipaddr：IP源站。
-   domain：域名源站。
-   oss：OSS Bucket为源站。

 |
|Weight|String|20|权重。

 |
|RequestId|String|09ABE829-6CD3-4FE0-AFEE-556113E29727|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://www.example.com?Action=DescribeDcdnDomainDetail
&DomainName=example.com
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDcdnDomainDetailResponse>
	  <RequestId>09ABE829-6CD3-4FE0-AFEE-556113E29727</RequestId>
	  <DomainDetail>
		    <Cname>bb.test.com.dcdn7mhp.com</Cname>
		    <ResourceGroupId>rg-acfmyuji4b6r4ry</ResourceGroupId>
		    <DomainStatus>online</DomainStatus>
		    <DomainName>bb.test.com</DomainName>
		    <Sources>
			      <Source>
				        <Enabled>online</Enabled>
				        <Port>80</Port>
				        <Type>oss</Type>
				        <Content>xxx.oss-cn-hangzhou.aliyuncs.com</Content>
				        <Priority>50</Priority>
			      </Source>
		    </Sources>
		    <GmtModified>2017-11-27T06:51:26Z</GmtModified>
		    <GmtCreated>2017-11-27T06:51:25Z</GmtCreated>
	  </DomainDetail>
</DescribeDcdnDomainDetailResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"09ABE829-6CD3-4FE0-AFEE-556113E29727",
	"DomainDetail":{
		"Cname":"bb.test.com.dcdn7mhp.com",
		"DomainStatus":"online",
		"ResourceGroupId":"rg-acfmyuji4b6r4ry",
		"DomainName":"bb.test.com",
		"Sources":{
			"Source":[
				{
					"Enabled":"online",
					"Port":80,
					"Type":"oss",
					"Content":"xxx.oss-cn-hangzhou.aliyuncs.com",
					"Priority":"50"
				}
			]
		},
		"GmtModified":"2017-11-27T06:51:26Z",
		"GmtCreated":"2017-11-27T06:51:25Z"
	}
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/dcdn)查看更多错误码。

