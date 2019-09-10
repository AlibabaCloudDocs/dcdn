# RefreshDcdnObjectCaches {#doc_api_dcdn_RefreshDcdnObjectCaches .reference}

调用RefreshDcdnObjectCaches刷新节点上的文件内容，刷新指定URL内容至Cache节点。支持URL批量刷新。

一个ID每天最多可提交2000条URL和100个目录预热刷新类请求。

刷新API每次最高提交1000条URL，且单域名每次最高提交100条URL。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=dcdn&api=RefreshDcdnObjectCaches&type=RPC&version=2018-01-15)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|RefreshDcdnObjectCaches|操作接口名。系统规定参数，取值：**RefreshDcdnObjectCaches**。

 |
|ObjectPath|String|是|example.com/image/1.png|刷新路径，多个URL用换行符（\\n）或（\\r\\n）分隔。

 |
|ObjectType|String|否|File|刷新类型。取值范围：

 -   **File**
-   **Directory**

 默认值：**File**

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RefreshTaskId|String|95248880|刷新返回的任务ID。多个ID用逗号（,）分隔。

 |
|RequestId|String|E5BD4B50-7A02-493A-AE0B-97B9024B4135|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
https://dcdn.aliyuncs.com&Action=RefreshDcdnObjectCaches
&ObjectPath=example.com/example.txt
&ObjectType=File
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<RefreshDcdnObjectCachesResponse>
	  <PushTaskId>95248880</PushTaskId>
	  <RequestId>E5BD4B50-7A02-493A-AE0B-97B9024B4135</RequestId>
</RefreshDcdnObjectCachesResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"PushTaskId":"95248880",
	"RequestId":"E5BD4B50-7A02-493A-AE0B-97B9024B4135"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|SingleRequest.OverLimit|A maximum of 1000 URLs are supported for each request.|一次最多只能提交1000个url。|
|400|InvalidObjectType.Malformed|The specified ObjectType is invalid.|不支持该ObjectType，请重新输入。|
|400|InvalidObjectPath.Malformed|The specified ObjectPath is invalid.|ObjectPath错误，请填写正确的ObjectPath。|
|400|QuotaExceeded.Refresh|Your refresh attempts have exceeded the daily limit.|超出当日刷新限制。今日刷新数已用完。您可以通过刷新接口查询今日的刷新次数。|
|400|InvalidExtensiveDomain.ValueNotSupported|The specified ExtensiveDomain is not supported.|不支持泛域名。|
|400|QuotaPerMinuteExceeded.Refresh|You tried to refresh too frequently; please try again later.|刷新太频繁，请稍后再试。|
|400|TooMany.Refresh|The refresh queue is full; please try again later.|域名正在刷新的个数已经达到上限，请稍后再试。|

访问[错误中心](https://error-center.aliyun.com/status/product/dcdn)查看更多错误码。

