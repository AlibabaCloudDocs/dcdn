# DescribeDcdnIpaDomainConfigs {#doc_api_dcdn_DescribeDcdnIpaDomainConfigs .reference}

调用DescribeDcdnIpaDomainConfigs查询域名配置，一次可查询过个功能配置。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=dcdn&api=DescribeDcdnIpaDomainConfigs&type=RPC&version=2018-01-15)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDcdnIpaDomainConfigs|操作接口名，系统规定参数，取值：**DescribeDcdnIpaDomainConfigs**。

 |
|DomainName|String|是|www.xxx.org.cn|您的加速域名。

 |
|FunctionNames|String|是|filetype\_based\_ttl\_set,set\_req\_host\_header|功能列表名称，用逗号（,）分隔。

 |

FunctionNames功能说明。

|名称

|说明

|
|----|----|
|referer\_white\_list\_set

|refer白名单

|
|referer\_black\_list\_set

|refer黑名单

|
|filetype\_based\_ttl\_set

|文件过期时间设置

|
|path\_based\_ttl\_set

|目录过期时间设置

|
|cc\_defense

|防CC攻击

|
|oss\_auth

|OSS鉴权Bucket

|
|ip\_black\_list\_set

|IP黑名单

|
|ip\_white\_list\_set

|IP白名单

|
|error\_page

|错误页面重定向

|
|tesla

|页面优化加速

|
|set\_req\_host\_header

|修改回源自定义头

|
|set\_hashkey\_args

|忽略url参数

|
|aliauth

|阿里鉴权

|
|set\_resp\_header

|设置响应头（浏览器端可见）

|
|video\_seek

|视频切片拖拽开关

|
|range

|Range请求功能

|
|gzip

|页面Gzip优化

|
|https\_force

|强制HTTPS跳转

|
|http\_force

|强制HTTP跳转

|
|alilive

|视频直播配置

|
|forward\_scheme

|静态协议跟随回源

|
|dynamic

|全站加速

|
|tmd\_signature

|TMD自定义规则

|
|websocket

|websocket

|

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DomainConfigs| | |域名配置。

 |
|ConfigId|String|5003576|配置ID。

 |
|FunctionArgs| | |各个function。

 |
|ArgName|String|file\_type|配置名称。

 |
|ArgValue|String|txt|配置值。

 |
|FunctionName|String|set\_req\_host\_header|function名称。

 |
|Status|String|success|状态，包括success、testing、failed、configuring。

 |
|RequestId|String|F8AA0364-0FDB-4AD5-AC74-D69FAB8924ED|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://dcdn.aliyuncs.com/?Action=DescribeDcdnIpaDomainConfigs
&DomainName=www.xxx.org.cn
&FunctionNames=filetype_based_ttl_set,set_req_host_header
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDcdnIpaDomainConfigsResponse>
	  <RequestId>F8AA0364-0FDB-4AD5-AC74-D69FAB8924ED</RequestId>
	  <DomainConfigs>
		    <DomainConfig>
			      <FunctionArgs>
				        <FunctionArg>
					          <ArgName>domain_name</ArgName>
					          <ArgValue>testdcdn3.cdnpe.com</ArgValue>
				        </FunctionArg>
			      </FunctionArgs>
			      <ConfigId>5003576</ConfigId>
			      <FunctionName>set_req_host_header</FunctionName>
		    </DomainConfig>
		    <DomainConfig>
			      <FunctionArgs>
				        <FunctionArg>
					          <ArgName>file_type</ArgName>
					          <ArgValue>txt</ArgValue>
				        </FunctionArg>
				        <FunctionArg>
					          <ArgName>ttl</ArgName>
					          <ArgValue>13</ArgValue>
				        </FunctionArg>
				        <FunctionArg>
					          <ArgName>weight</ArgName>
					          <ArgValue>8</ArgValue>
				        </FunctionArg>
			      </FunctionArgs>
			      <ConfigId>5068995</ConfigId>
			      <FunctionName>filetype_based_ttl_set</FunctionName>
		    </DomainConfig>
	  </DomainConfigs>
</DescribeDcdnIpaDomainConfigsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"F8AA0364-0FDB-4AD5-AC74-D69FAB8924ED",
	"DomainConfigs":{
		"DomainConfig":[
			{
				"FunctionArgs":{
					"FunctionArg":[
						{
							"ArgName":"domain_name",
							"ArgValue":"testdcdn3.cdnpe.com"
						}
					]
				},
				"FunctionName":"set_req_host_header",
				"ConfigId":5003576
			},
			{
				"FunctionArgs":{
					"FunctionArg":[
						{
							"ArgName":"file_type",
							"ArgValue":"txt"
						},
						{
							"ArgName":"ttl",
							"ArgValue":"13"
						},
						{
							"ArgName":"weight",
							"ArgValue":"8"
						}
					]
				},
				"FunctionName":"filetype_based_ttl_set",
				"ConfigId":5068995
			}
		]
	}
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|Invalid%s.ValueNotSupported|FunctionName \[%s\] is not supported.|不支持该配置，请重新查询。|

访问[错误中心](https://error-center.aliyun.com/status/product/dcdn)查看更多错误码。

