# DeleteDcdnDomain {#doc_api_dcdn_DeleteDcdnDomain .reference}

调用DeleteDcdnDomain删除已添加的加速域名。

 **调用该接口前，请您注意：** 

-   请慎重操作，以免导致删除操作后此域名不可访问。建议您在进行域名删除前到域名解析服务商处恢复域名A记录。
-   调用**DeleteDcdnDomain**成功后将删除本条加速域名的全部相关记录，对于仅需要暂停使用该加速域名，推荐**StopDcdnDomain**接口。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=dcdn&api=DeleteDcdnDomain&type=RPC&version=2018-01-15)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DeleteDcdnDomain|操作接口名，系统规定参数。取值：**DeleteDcdnDomain**。

 |
|DomainName|String|是|example.com|要删除的域名。

 |
|ResourceGroupId|String|否|123|资源组ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|0AEDAF20-4DDF-4165-8750-47FF9C1929C9|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://http://dcdn.aliyuncs.com?Action=DeletDcdnDomain
&DomainName=example.com
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DeleteDcdnDomainResponse>
	  <RequestId>0AEDAF20-4DDF-4165-8750-47FF9C1929C9</RequestId>
</DeleteDcdnDomainResponse>
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
|400|InvalidDomainName.Malformed|The specified DomainName is invalid.|域名格式错误。|

访问[错误中心](https://error-center.aliyun.com/status/product/dcdn)查看更多错误码。

