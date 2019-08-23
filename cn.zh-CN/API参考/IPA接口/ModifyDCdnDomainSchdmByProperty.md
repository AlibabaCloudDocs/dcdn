# ModifyDCdnDomainSchdmByProperty {#doc_api_dcdn_ModifyDCdnDomainSchdmByProperty .reference}

调用ModifyDCdnDomainSchdmByProperty修改加速域名。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=dcdn&api=ModifyDCdnDomainSchdmByProperty&type=RPC&version=2018-01-15)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ModifyDCdnDomainSchdmByProperty|操作接口名，系统规定参数。取值：**ModifyDCdnDomainSchdmByProperty**。

 |
|DomainName|String|是|example.com|需修改加速区域的域名。

 |
|Property|String|是|domestic|调度域属性，\{"coverage":"overseas"\} 中coverage支持**domestic**、**overseas**、**global**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|15C66C7B-671A-4297-9187-2C4477247A74|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://dcdn.aliyuncs.comAction=ModifyDCdnDomainSchdmByProperty
&DomainName=example.com
&property={"coverage":"overseas"}
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ModifyDCdnDomainSchdmByPropertyResponse>
	  <RequestId>15C66C7B-671A-4297-9187-2C4477247A74</RequestId>
</ModifyDCdnDomainSchdmByPropertyResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"15C66C7B-671A-4297-9187-2C4477247A74"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|Schedule.NotFound|This domain does not have any available CDN resources in the accelerated area.|域名无可用调度域资源|
|400|DomainTraffic.ExceedThreshold|You are not allowed to perform this operation because the traffic peak of the last day exceeds the threshold.|域名昨日峰值超限不可切换|
|400|Domain.BeianInvalid|You are not allowed to perform this operation because the ICP license of your domain is invalid in Chinese Mainland.|域名中国大陆区域备案无效|
|400|Schedule.ChangeFail|Failed to change the accelerated area for the domain.|域名切换调度区域失败|

访问[错误中心](https://error-center.aliyun.com/status/product/dcdn)查看更多错误码。

