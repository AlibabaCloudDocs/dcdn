# DescribeDcdnUserQuota {#doc_api_dcdn_DescribeDcdnUserQuota .reference}

调用DescribeDcdnUserQuota查询用户资源上限及已使用情况。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=dcdn&api=DescribeDcdnUserQuota&type=RPC&version=2018-01-15)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDcdnUserQuota|操作接口名，系统规定参数，取值：**DescribeDcdnUserQuota**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|BlockQuota|Integer|20|封禁上限。

 |
|BlockRemain|Integer|500|封禁余量。

 |
|DomainQuota|Integer|50|加速域名数上限。

 |
|PreloadQuota|Integer|500|预热上限。

 |
|PreloadRemain|Integer|300|预热上限。

 |
|RefreshDirQuota|Integer|100|刷新目录上限。

 |
|RefreshDirRemain|Integer|100|刷新目录余量。

 |
|RefreshUrlQuota|Integer|100|刷新URL上限。

 |
|RefreshUrlRemain|Integer|100|刷新URL余量。

 |
|RequestId|String|BFFCDFAD-DACC-484E-9BE6-0AF3B3A0DD23|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
https://dcdn.aliyuncs.com?&Action=DescribeDcdnUserQuota
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDcdnUserQuotaResponse>
	  <DomainQuota>20</DomainQuota>
	  <RefreshUrlQuota>1000</RefreshUrlQuota>
	  <RefreshDirQuota>500</RefreshDirQuota>
	  <RefreshUrlRemain>500</RefreshUrlRemain>
	  <RefreshDirRemain>300</RefreshDirRemain>
	  <PreloadQuota>300</PreloadQuota>
	  <PreloadRemain>100</PreloadRemain>
	  <BlockQuota>100</BlockQuota>
	  <BlockRemain>100</BlockRemain>
	  <RequestId>BFFCDFAD-DACC-484E-9BE6-0AF3B3A0DD23</RequestId>
</DescribeDcdnUserQuotaResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"PreloadRemain":100,
	"RefreshUrlRemain":500,
	"DomainQuota":20,
	"RefreshDirRemain":300,
	"RequestId":"BFFCDFAD-DACC-484E-9BE6-0AF3B3A0DD23",
	"BlockRemain":100,
	"RefreshUrlQuota":1000,
	"BlockQuota":100,
	"PreloadQuota":300,
	"RefreshDirQuota":500
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/dcdn)查看更多错误码。

