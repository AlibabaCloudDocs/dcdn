# BatchSetDcdnIpaDomainConfigs {#doc_api_dcdn_BatchSetDcdnIpaDomainConfigs .reference}

调用BatchSetDcdnIpaDomainConfigsIP4层应用加速域名批量配置。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=dcdn&api=BatchSetDcdnIpaDomainConfigs&type=RPC&version=2018-01-15)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|BatchSetDcdnIpaDomainConfigs|操作接口名，系统规定参数。取值：**BatchSetDcdnIpaDomainConfigs**。

 |
|DomainNames|String|是|example.com|您的IP4层应用加速域名，多个用逗号（,）分隔。

 |
|Functions|String|是|\[\{"functionArgs":\[\{"argName":"domain\_name","argValue":"api.hellodtworld.com"\}\],"functionName":"set\_req\_host\_header"\}\]|功能列表。

 |

某些功能，如filetype\_based\_ttl\_set，可以设置多条纪录，当需要更新其中某条纪录时，可通过该条纪录的configId来指定。

\{"functionArgs":\[\{"argName":"file\_type","argValue":"jpg"\},\{"argName":"ttl","argValue":"18"\},\{"argName":"weight","argValue":"30"\},"functionName":"filetype\_based\_ttl\_set","configId":5068995\}\]

|名称

|参数

|
|----|----|
|referer\_white\_list\_set：refer白名单

|refer\_domain\_allow\_list：白名单列表，多个逗号（,）分隔；

 allow\_empty 是否允许空refer进入，取值范围：on/off

 |
|referer\_black\_list\_set：refer黑名单

|refer\_domain\_deny\_list：黑名单列表，多个逗号（,）分隔；

 allow\_empty 是否允许空refer进入，取值范围：on/off

 |
|filetype\_based\_ttl\_set：文件过期时间设置

|ttl：cache时间，单位：秒；

 file\_type：文件类型：支持多个用逗号（,）隔开，如txt,jpg；

 weight：权重：取值范围1~199

 |
|path\_based\_ttl\_set：目录过期时间设置

|ttl：cache时间，单位：秒。

 path：目录，必须以正斜线（/）开头。

 weight：权重：取值范围1~99。

 |
|oss\_auth：OSS鉴权Bucket

|oss\_bucket\_id：用户bucket地址

|
|ip\_black\_list\_set：IP黑名单

|ip\_list：IP列表多个用逗号（,）隔开

|
|ip\_allow\_list\_set：IP白名单

|ip\_list：IP列表多个用逗号（,）隔开

|
|ip\_white\_list\_set：TMD免拦截

|ip\_list：IP列表多个用逗号（,）隔开

|
|error\_page：错误页面重定向

|error\_code：错误码；

 rewrite\_page：重定向页面

 |
|set\_req\_host\_header：修改回源自定义头

|domain\_name：回源Host头内容

|
|set\_hashkey\_args：忽略url参数

|hashkey\_args：保留参数的列表，多个用逗号（,）分隔；

 disable：disable等于on的时候表示忽略所有参数，off不忽略

 |
|aliauth：阿里鉴权

|auth\_type：鉴权类型，取值范围"no\_auth","type\_a","type\_b","type\_c"；

 auth\_key1：鉴权key1；auth\_key2：鉴权key2；

 ali\_auth\_delta：自定义鉴权缓冲时间

 |
|set\_resp\_header：设置响应头（浏览器端可见）

|key：响应头，取值范围：Content-Type、Cache-Control、Content-Disposition、Content-Language、Expires、Access-Control-Allow-Origin、Access-Control-Allow-Methods、Access-Control-Allow-Headers、Access-Control-Max-Age、Access-Control-Expose-Headers；

 value：响应头内容，删除填写null

 |
|https\_force：强制HTTPS跳转

|enable：功能开关，取值范围：on/off

|
|http\_force：强制HTTP跳转

|enable：功能开关，取值范围：on/off

|
|https\_option：HTTPS基础参数

|http2：http2开关，取值范围：on/off

|
|l2\_oss\_key：L2 OSS 回源私钥

|private\_oss\_auth：是否开启私有oss鉴权功能，取值范围：on/off

|
|forward\_scheme：静态协议跟随回源

|enable：开关，取值范围：on/off

 scheme\_origin：回源站协议，支持http、https和follow

 |
|green\_manager 鉴黄功能

|enable：是否开启鉴黄功能，取值范围：on/off

|
|tmd\_signature：TMD自定义规则

|name：规则名称，域名内不可重复

 path：可重复，需校验uri路径合法性

 pathType：匹配规则，0 前缀匹配，1 完全匹配

 interval：监测时长，单位秒，参数限制必须\>=10

 count：单IP访问次数

 action：阻断类型，0 封禁，1 人机识别

 ttl:阻断时长，单位秒

 |
|dynamic：全站加速相关配置

|enable：必填，开关，支持on/off；

 static\_route\_type:静态加速文件后缀

 static\_route\_url:静态加速URI

 static\_route\_path:静态加速PATH

 dynamic\_route\_origin:回源路由 scheme，支持http、https和follow

 |
|set\_req\_header：自定义回源HTTP头

|key：回源头；

 value:回源头内容

 |
|l2\_oss\_key：私有buckct回源

|private\_oss\_auth：私有Bucket回源开关，支持on/off

|
|range：range回源

|enable：开关，支持on/off

|
|video\_seek：视频拖拽播放

|enable：开关，支持on/off

|
|websocket：Websocket

|enabled：必填，是否开启，取值范围：on/off

 origin\_scheme：回源scheme，支持http、https和follow

 heartbeat：心跳时间，默认60，支持1-300秒

 |
|ali\_remove\_args：忽略url参数\(删除\)

|ali\_remove\_args：必填，删除指定的参数，多个参数之间用空格隔开，剩余参数将作为hashkey中URL args部分；keep\_oss\_args:支持on/off.on表示回源保留所有参数，off表示与缓存hashkey的参数一致

|
|https\_tls\_version：TLS协议版本

|tls10：开启 TLSv1.0 默认:on，支持on/off；

 tls11:开启 TLSv1.1 默认:on，支持on/off

 tls12:开启 TLSv1.2 默认:on，支持on/off

 tls13:开启 TLSv1.3 默认:off，支持on/off

 |
|HSTS：HSTS

|enabled：必填，开关，默认: off，支持on/off；

 https\_hsts\_max\_age:必填，过期时间，单位：ms，建议填写5184000000ms\(60天\)

 https\_hsts\_include\_subdomains:HSTS 头包含 includeSubDomains 参数,支持on/off。请谨慎开启，开启前，请确保该加速域名所有子域名都已开启 HTTPS，否则会导致子域名自动跳转到 HTTPS 后无法访问

 |
|filetype\_force\_ttl\_code:文件状态码过期时间设置

|file\_type：必填，文件类型：支持多个，用逗号（,）隔开，如txt,jpg；code\_string：必填，状态码，例：302=0,301=0,4xx=2

|
|path\_force\_ttl\_code:路径状态码过期时间设置

|path：必填，必须以/开头，举例：/image；code\_string：必填，状态码，例：302=0,301=0,4xx=2

|
|gzip:页面Gzip优化

|enable：必填，功能开关，支持on/off

|
|tesla:页面优化加速

|enable：必填，功能开关，支持on/off

|
|protogw:IP应用加速

|realip：必填，源站ip透传方式，支持off/toa/pp。port：必填，服务端口

|

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|0AEDAF20-4DDF-4165-8750-47FF9C1929C9|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://dcdn.aliyuncs.com/?Action=BatchSetDcdnIpaDomainConfigs
&DomainName=example1.com,example2.com
&Functions=[{"functionArgs":[{"argName":"domain_name","argValue":"api.hellodtworld.com"}],"functionName":"set_req_host_header"}]
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<BatchSetDcdnIpaDomainConfigsResponse>
	  <RequestId>0AEDAF20-4DDF-4165-8750-47FF9C1929C9</RequestId>
</BatchSetDcdnIpaDomainConfigsResponse>
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
|400|InvalidFunctions.Malformed|The specified Functions is invalid.|不支持该配置，请重新填写。|
|400|InvalidArgValue.Malformed|The specified ArgValue is invalid.|ArgValue错误，请重新填写。|
|400|Invalid%s.ValueNotSupported|\[%s\] is not supported.|不支持该设置。|
|400|Invalid%s.Malformed|The specified ArgValue \[%s\] is invalid.|不支持该ArgValue，请填写正确的ArgValue。|
|403|DcdnIpaServiceNotFound|The DCDN IPA service has not been activated.|没有开通Dcdn Ipa服务。|

访问[错误中心](https://error-center.aliyun.com/status/product/dcdn)查看更多错误码。

