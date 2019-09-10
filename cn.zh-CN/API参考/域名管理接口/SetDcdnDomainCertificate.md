# SetDcdnDomainCertificate {#doc_api_dcdn_SetDcdnDomainCertificate .reference}

调用SetDcdnDomainCertificate设置某域名下证书功能是否启用，以及修改证书信息。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=dcdn&api=SetDcdnDomainCertificate&type=RPC&version=2018-01-15)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|SetDcdnDomainCertificate|操作接口名。系统规定参数。取值：**SetDcdnDomainCertificate**。

 |
|DomainName|String|是|example.com|指定证书所属加速域名。需属于HTTPS加速类型。

 |
|SSLProtocol|String|是|on|HTTPS证书是否启用。默认值：**off**。取值范围：

 -   **on**：启用。
-   **off**：不启用。

 |
|CertName|String|否|yourCertName|证书名称。

 |
|CertType|String|否|cas|证书类型。取值范围：

 -   **upload**：上传证书。
-   **cas**：证书中心证书。
-   **free**：免费证书。

 |
|ForceSet|String|否|1|设置为1时，忽略证书名称重复的校验，覆盖原有同名证书信息。

 |
|Region|String|否|cn-shanghai|地区信息。

 |
|SSLPri|String|否|SSLPri|私钥内容。不启用证书则无需输入，配置证书请输入私钥内容。

 |
|SSLPub|String|否|SSLPub|安全证书内容。不启用证书则无需输入，配置证书请输入证书内容。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|0AEDAF20-4DDF-4165-8750-47FF9C1929C9|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://dcdn.aliyuncs.comAction=SetDcdnDomainCertificate
&DomainName=example.com
&SSLProtocol=on
&SSLPub=xxx
&SSLPri=yyy
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<SetDcdnDomainCertificateResponse>
	  <RequestId>0AEDAF20-4DDF-4165-8750-47FF9C1929C9</RequestId>
</SetDcdnDomainCertificateResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"0AEDAF20-4DDF-4165-8750-47FF9C1929C9"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidSSLProtocol.ValueNotSupported|The specified SSLProtocol is invalid.|不支持该HTTPS证书开关，请填写on或off。|
|400|SSLPub.MissingParameter|The SSLPub parameter is required.|请填写SSLPub。|
|400|SSLPri.MissingParameter|The SSLPri parameter is required.|请填写SSLPri。|
|400|InvalidSSLPub|The specified SSLPub is invalid.|SSLPub错误，请重新填写。|
|400|InvalidSSLPri|The specified SSLPri is invalid.|SSLPri错误，请填写正确的SSLPri。|
|400|Certificate.MissMatch|The SSLPri does not match the certificate.|证书与私钥不匹配。|
|400|InvalidCertificate.TooLong|The maximum length of the certificate is exceeded.|Certificate长度超过限制。|
|400|InvalidCertName.TooLong|The length of the certificate name cannot exceed 128 characters.|证书名称不能超过128个字符。|
|400|IllegalOperationDomain|You are not authorized to operate the domain.|您没有权限操作该域名。|
|400|AuthenticationFailed|Error performing verification.|身份验证失败。|
|400|SetDomainCertificate.ParameterError|The specified parameters are invalid.|参数错误，请填写正确的参数再重试。|
|400|Certificate.StatusError|The status of the certificate is invalid.|证书状态错误。|
|400|DeleteFailed|Error deleting the certificate.|删除证书失败。|
|400|Certificate.NotFind|The certificate does not exist.|证书不存在。|
|400|Certificate.Duplicated|The certificate name already exists.|证书重复。|
|400|Certificate.FormatError|The format of the certificate is invalid.|证书格式错误。|
|400|Certificate.StatusError|The certificate does not exist, or the status of the certificate is invalid.|证书不存在或证书状态错误。|
|400|Certificate.KeyNull|The private key is required.|私钥不能为空。|
|400|Key.Malformed|The specified Key format is invalid.|参数Key 格式错误。|
|400|CertStorage.failed|Error saving the certificate.|证书保存失败。|
|400|CertificateContent.Duplicated|The certificate has been uploaded; do not upload again.|证书已经上传，请不要再次上传。|
|400|Certificate.Expired|The certificate has expired.|证书过期了|
|400|InvalidDomain.notOnline|The domain is offline. Check the status of the domain and try again later.|域名未在线，请检查域名状态，稍后再试。|
|400|Decode.Error|Error decoding the SSLPub or SSLPri certificate.|证书 sslpub 或 sslpri 解码错误。|
|400|sslPub.Error|Error encoding SSLPub.|sslPub 编码失败。|
|400|sslPri.Error|Error encoding SSLPri.|sslPri 编码失败。|
|400|DomainInSafeMode|The domain is in safe mode. To request permission, contact Customer Service.|此域名处于安全模式。如果您想做这个操作，请工单联系我们。|
|403|DomainInProtectedMode|The domain is in protection mode. To request permission, contact Customer Service.|此域名处于被保护模式。如果您想做这个操作，请联系我们。|

访问[错误中心](https://error-center.aliyun.com/status/product/dcdn)查看更多错误码。

