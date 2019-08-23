# DescribeDcdnRefreshQuota {#doc_api_dcdn_DescribeDcdnRefreshQuota .reference}

调用DescribeDcdnRefreshQuota查询当日剩余刷新、预热URL及目录的次数。

刷新预热类接口包含**RefreshDcdnObjectCaches**刷新接口和**PreloadDcdnObjectCaches**预热接口。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=dcdn&api=DescribeDcdnRefreshQuota&type=RPC&version=2018-01-15)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDcdnRefreshQuota|操作接口名。系统规定参数，取值：**DescribeDcdnRefreshQuota**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|BlockQuota|String|100|封禁上限。

 |
|DirQuota|String|100|当天路径刷新数量上限。

 |
|DirRemain|String|99|当天剩余目录刷新数量。

 |
|PreloadQuota|String|100|当天预热数量上限。

 |
|PreloadRemain|String|100|当天剩余预热数量。

 |
|RequestId|String|42E0554B-80F4-4921-AED6-ACFB22CAAAD0|请求ID。

 |
|UrlQuota|String|2000|当天URL刷新数量上限。

 |
|UrlRemain|String|1996|当天剩余url刷新数量。

 |
|blockRemain|String|100|封禁余量。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
http://dcdn.aliyuncs.com??Action=DescribeDcdnRefreshQuota
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDcdnRefreshQuotaResponse>
	  <DirQuota>100</DirQuota>
	  <DirRemain>99</DirRemain>
	  <RequestId>42E0554B-80F4-4921-AED6-ACFB22CAAAD0</RequestId>
	  <UrlQuota>2000</UrlQuota>
	  <UrlRemain>1996</UrlRemain>
	  <PreloadQuota>500</PreloadQuota>
	  <PreloadRemain>400</PreloadRemain>
</DescribeDcdnRefreshQuotaResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"DirQuota":"100",
	"PreloadRemain":"400",
	"DirRemain":"99",
	"RequestId":"42E0554B-80F4-4921-AED6-ACFB22CAAAD0",
	"UrlQuota":"2000",
	"UrlRemain":"1996",
	"PreloadQuota":"500"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/dcdn)查看更多错误码。

