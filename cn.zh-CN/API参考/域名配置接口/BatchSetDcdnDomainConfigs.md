# BatchSetDcdnDomainConfigs {#doc_api_dcdn_BatchSetDcdnDomainConfigs .reference}

调用BatchSetDcdnDomainConfigs实现域名批量配置功能。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=dcdn&api=BatchSetDcdnDomainConfigs&type=RPC&version=2018-01-15)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|BatchSetDcdnDomainConfigs|操作接口名，系统规定参数，取值：**BatchSetDcdnDomainConfigs**。

 |
|DomainNames|String|是|example.com|您的加速域名，多个用逗号（,）分隔。

 |
|Functions|String|是|\[\{"functionArgs":\[\{"argName":"domain\_name","argValue":"api.hellodtworld.com"\}\],"functionName":"set\_req\_host\_header"\}\]|功能列表。

 |

Functions功能说明：所有参数值均按照字符串类型处理。

某些功能，如filetype\_based\_ttl\_set，可以设置多条纪录，当需要更新其中某条纪录时，可通过该条纪录的configId来指定。\{"functionArgs":\[\{"argName":"file\_type","argValue":"jpg"\},\{"argName":"ttl","argValue":"18"\},\{"argName":"weight","argValue":"30"\},"functionName":"filetype\_based\_ttl\_set","configId":5068995\}\]

功能列表如下所示。

|名称

|参数

|
|----|----|
|referer\_white\_list\_set：refer白名单

|refer\_domain\_allow\_list：白名单列表，多个逗号（,）分隔。

 allow\_empty：是否允许空refer进入，取值范围：on/off。

 |
|referer\_black\_list\_set：refer黑名单

|refer\_domain\_deny\_list：黑名单列表，多个逗号（,）分隔。

 allow\_empty：是否允许空refer进入，取值范围：on/off。

 |
|filetype\_based\_ttl\_set：文件过期时间设置

|ttl：cache时间，单位：秒。

 file\_type：支持多个文件类型。用逗号（,）隔开。例如：txt,jpg。weight：权重。取值范围：1~199。

 |
|path\_based\_ttl\_set：目录过期时间设置

|ttl：cache时间，单位：秒。

 path：目录，必须以正斜线（/）开头。

 weight：权重。取值范围：1~99。

 |
|oss\_auth：OSS鉴权Bucket

|oss\_bucket\_id：用户bucket地址。

|
|ip\_black\_list\_set：IP黑名单

|ip\_list：IP列表多个用逗号（,）隔开。

|
|ip\_allow\_list\_set：IP白名单

|ip\_list：IP列表多个用逗号（,）隔开。

|
|ip\_white\_list\_set：TMD免拦截

|ip\_list：IP列表多个用逗号（,）隔开。

|
|error\_page：错误页面重定向

|error\_code：错误码。rewrite\_page：重定向页面。

|
|set\_req\_host\_header：修改回源自定义头

|domain\_name：回源Host头内容。

|
|set\_hashkey\_args：忽略url参数

|hashkey\_args：保留参数的列表，多个用逗号（,）分隔。

 disable：disable等于on表示忽略所有参数，等于off表示不忽略。

 |
|aliauth：阿里鉴权

|auth\_type：鉴权类型。取值范围：”no\_auth”、”type\_a”、”type\_b”、”type\_c”

 auth\_key1：鉴权key1。auth\_key2：鉴权key2。

 ali\_auth\_delta：自定义鉴权缓冲时间。

 |
|set\_resp\_header：设置响应头（浏览器端可见）

|key：响应头。value：响应头内容，删除填写null。

|
|https\_force：强制HTTPS跳转

|enable：功能开关，取值范围：on/off。

|
|http\_force：强制HTTP跳转

|enable：功能开关，取值范围：on/off。

|
|https\_option：HTTPS基础参数

|http2：http2开关，取值范围：on/off。

|
|l2\_oss\_key：L2 OSS 回源私钥

|private\_oss\_auth：是否开启私有oss鉴权功能，取值范围：on/off。

|
|forward\_scheme：swift自适应回源

|enable：开关，取值范围：on/off。

 scheme\_origin：回源站协议，支持http、https和follow。

 |
|green\_manager 鉴黄功能

|enable：是否开启鉴黄功能，取值范围：on/off。

|
|tmd\_signature：TMD自定义规则

|name：规则名称，域名内不可重复。

 path：可重复，需校验uri路径合法性。

 pathType：匹配规则。0表示前缀匹配，1表示完全匹配。interval：监测时长，单位秒，参数限制必须≥10。

 count：单IP访问次数。

 action：阻断类型。0表示封禁，1表示人机识别。ttl：阻断时长。单位：秒。

 |
|dynamic：全站加速相关配置

|enable：开关。必填，支持on/off。

 static\_route\_type：静态加速文件后缀。

 static\_route\_url：静态加速URI。

 static\_route\_path：静态加速PATH。

 dynamic\_route\_origin：回源路由scheme，支持http、https和follow。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|04F0F334-1335-436C-A1D7-6C044FE73368|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://dcdn.aliyuncs.com/?Action=BatchSetDcdnDomainConfigs
&DomainName=example.com
&Functions=[{"functionArgs":[{"argName":"domain_name","argValue":"api.hellodtworld.com"}],"functionName":"set_req_host_header"}]
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<BatchSetDcdnDomainConfigsResponse>
	  <RequestId>04F0F334-1335-436C-A1D7-6C044FE73368</RequestId>
</BatchSetDcdnDomainConfigsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"04F0F334-1335-436C-A1D7-6C044FE73368"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidFunctions.Malformed|The specified Functions is invalid.|不支持该配置，请重新填写。|
|400|InvalidArgValue.Malformed|The specified ArgValue is invalid.|ArgValue错误，请重新填写。|
|400|Invalid%s.ValueNotSupported|\[%s\] is not supported.|不支持该设置。|
|400|Invalid%s.Malformed|The specified ArgValue \[%s\] is invalid.|不支持该ArgValue，请填写正确的ArgValue。|

访问[错误中心](https://error-center.aliyun.com/status/product/dcdn)查看更多错误码。

