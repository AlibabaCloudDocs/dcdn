# DescribeDcdnIpaDomainDetail {#doc_api_dcdn_DescribeDcdnIpaDomainDetail .reference}

调用DescribeDcdnIpaDomainDetail获取指定加速域名配置的基本信息

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=dcdn&api=DescribeDcdnIpaDomainDetail&type=RPC&version=2018-01-15)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDcdnIpaDomainDetail|操作接口名，系统规定参数。取值：**DescribeDcdnIpaDomainDetail**。

 |
|DomainName|String|是|example.com|接入全站加速IPA进行加速的域名。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DomainDetail| | |域名详情。

 |
|CertName|String|yourCertName|如果开启https，此处为证书名称。

 |
|Cname|String|example.com|为加速域名生成的一个CNAME域名，需要在域名解析服务商处将加速域名CNAME解析到该域名。

 |
|Description|String|audit failed|描述。

 |
|DomainName|String|example.com|接入全站加速IPA进行加速的域名。

 |
|DomainStatus|String|online|加速域名运行状态。

 -   **online**：启用。
-   **offline**：停用。
-   **configuring**：配置中。
-   **configure\_failed**：配置失败。
-   **checking**：正在审核。
-   **check\_failed**：审核失败。

 |
|GmtCreated|String|2017-11-27T06:51:26Z|创建时间。

 |
|GmtModified|String|2017-11-27T06:51:26Z|最近修改时间。

 |
|ResourceGroupId|String|rg-acfmyuji4b6r4ry|资源组ID。

 |
|SSLProtocol|String|on|是否开启ssl证书。**on**表示开启；**off**表示关闭。

 |
|SSLPub|String|SSLPub|如果开启https，此处为证书公钥。

 |
|Scope|String|overseas。|区域。

 |
|Sources| | |源站信息。

 |
|Content|String|xxx.oss-cn-hangzhou.aliyuncs.com|回源地址。

 |
|Enabled|String|online|状态。

 |
|Port|Integer|80|自定义端口，范围：**0**~**65535**。

 |
|Priority|String|50|优先级。

 |
|Type|String|oss|源站类型。取值：

 -   **ipaddr**：IP源站。
-   **domain**：域名源站。
-   **oss**：不支持oss。

 |
|Weight|String|10|回源权重。

 |
|RequestId|String|09ABE829-6CD3-4FE0-AFEE-556113E29727|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://dcdn.aliyuncs.com?Action=DescribeDcdnIpaDomainDetail
&DomainName=example.com
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDcdnIpaDomainDetailResponse>
	  <RequestId>09ABE829-6CD3-4FE0-AFEE-556113E29727</RequestId>
	  <DomainDetail>
		    <Cname>example.com.dcdn7mhp.com</Cname>
		    <ResourceGroupId>rg-acfmyuji4b6r4ry</ResourceGroupId>
		    <DomainStatus>online</DomainStatus>
		    <DomainName>example.com</DomainName>
		    <Sources>
			      <Source>
				        <Enabled>online</Enabled>
				        <Port>80</Port>
				        <Type>oss</Type>
				        <Content>xxx.oss-cn-hangzhou.aliyuncs.com</Content>
				        <Priority>50</Priority>
				        <Weight>10</Weight>
			      </Source>
		    </Sources>
		    <GmtModified>2017-11-27T06:51:26Z</GmtModified>
		    <GmtCreated>2017-11-27T06:51:25Z</GmtCreated>
	  </DomainDetail>
</DescribeDcdnIpaDomainDetailResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"09ABE829-6CD3-4FE0-AFEE-556113E29727",
	"DomainDetail":{
		"Cname":"example.com.dcdn7mhp.com",
		"DomainStatus":"online",
		"ResourceGroupId":"rg-acfmyuji4b6r4ry",
		"DomainName":"example.com",
		"Sources":{
			"Source":[
				{
					"Enabled":"online",
					"Port":80,
					"Weight":"10",
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

