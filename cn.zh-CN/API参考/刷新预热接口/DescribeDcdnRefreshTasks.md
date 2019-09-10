# DescribeDcdnRefreshTasks {#doc_api_dcdn_DescribeDcdnRefreshTasks .reference}

调用DescribeDcdnRefreshTasks查询刷新、预热状态是否在全网生效。

 **调用该接口前，请您注意：** 

-   支持根据任务ID或URL查询。
-   Taskid与Objectpath都不指定，默认查3天内、第一页的数据（20条）。
-   Taskid与Objectpath可以同时指定。
-   当指定DomainName或TaskStatus时，必须填写ObjectType。
-   只可查询3天内的数据。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=dcdn&api=DescribeDcdnRefreshTasks&type=RPC&version=2018-01-15)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDcdnRefreshTasks|操作接口名。系统规定参数。取值：**DescribeDcdnRefreshTasks**。

 |
|DomainName|String|否|example.com|域名。

 |
|EndTime|String|否|2017-01-01T12:12:20Z|结束时间。

 |
|ObjectPath|String|否|http://aaa.com/1.txt|按路径查询，准确匹配。

 |
|ObjectType|String|否|file|任务类型。取值范围：

 -   **file**
-   **path**
-   **preload**

 当指定DomainName或TaskStatus时，此项必填。

 |
|PageNumber|Integer|否|2|取得页数。取值范围为：**1**~**100000**。

 |
|PageSize|Integer|否|20|分页大小。默认值：**20**，最大值：**50**，取值范围：**1**~**50**之前的任意整数。

 |
|ResourceGroupId|String|否|123|资源组ID。

 |
|StartTime|String|否|2017-01-01T12:12:20Z|开始时间。

 |
|Status|String|否|Complete|任务状态：

 -   **Complete**：完成。
-   **Refreshing**：刷新中。
-   **Failed**：刷新失败。

 |
|TaskId|String|否|123|按任务ID查询刷新状态。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|PageNumber|Long|2|页码。

 |
|PageSize|Long|2|整页大小。

 |
|RequestId|String|174F6032-AA26-470D-B90E-36F0EB205BEE|请求ID。

 |
|Tasks| | |Task组成的Task任务列表。

 |
|CreationTime|String|2014-11-27T08:23:22Z|任务对象创建时间。为UTC时间。

 |
|Description|String|Internal Error|刷新预热失败返回错误描述。取值范围：

 -   **InternalError**
-   **OriginTimeout**
-   **OriginReturn StatusCode 5XX**

 |
|ObjectPath|String|http://aaa.com/1.txt|刷新对象路径。

 |
|ObjectType|String|file|任务类型。取值范围：

 -   **file**
-   **path**
-   **preload**

 |
|Process|String|10|进度百分比。

 |
|Status|String|Complete|状态。取值范围：

 -   **Complete**：完成。
-   **Refreshing**：刷新中。
-   **Failed**：刷新失败。
-   **Pending**：等待刷新。

 |
|TaskId|String|123|任务ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}
https://dcdn.aliyuncs.com?&Action=DescribeDcdnRefreshTasks
&ObjectPath=
&PageNumber=1
&PageSize=10
&<公共请求参数>
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDcdnRefreshTasksResponse>
	  <Tasks>
		    <Task>
			      <CreationTime>2014-11-27T08:23:22Z</CreationTime>
			      <ObjectPath>http://aaa.com/1.txt</ObjectPath>
			      <Status>Complete</Status>
			      <TaskId>704225667</TaskId>
			      <ObjectType>file</ObjectType>
			      <Process>100%</Process>
		    </Task>
		    <Task>
			      <CreationTime>2014-11-27T08:18:38Z</CreationTime>
			      <ObjectPath>http://bbb.com/1.txt</ObjectPath>
			      <Status>Complete</Status>
			      <TaskId>704222904</TaskId>
			      <ObjectType>file</ObjectType>
			      <Process>100%</Process>
		    </Task>
	  </Tasks>
	  <PageNumber>1</PageNumber>
	  <PageSize>10</PageSize>
	  <TotalCount>2</TotalCount>
	  <RequestId>174F6032-AA26-470D-B90E-36F0EB205BEE</RequestId>
</DescribeDcdnRefreshTasksResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"TotalCount":2,
	"PageSize":10,
	"RequestId":"174F6032-AA26-470D-B90E-36F0EB205BEE",
	"Tasks":{
		"Task":[
			{
				"ObjectPath":"http://aaa.com/1.txt",
				"CreationTime":"2014-11-27T08:23:22Z",
				"Status":"Complete",
				"ObjectType":"file",
				"Process":"100%",
				"TaskId":"704225667"
			},
			{
				"ObjectPath":"http://bbb.com/1.txt",
				"CreationTime":"2014-11-27T08:18:38Z",
				"Status":"Complete",
				"ObjectType":"file",
				"Process":"100%",
				"TaskId":"704222904"
			}
		]
	}
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidTaskId.Malformed|The specified TaskId is invalid.|TaskId错误，请填写正确的TaskId。|
|400|MissingTimeParameter|The StartTime and EndTime must be both specified.|请同时提供开始时间和结束时间。|
|400|MissingParameter.ObjectType|The ObjectType parameter is required if DomainName or ObjectType is specified.|请填写ObjectType。|
|400|InvalidStartTime.Malformed|The specified StartTime is invalid.|请提供正确的开始时间格式。日期格式按照ISO8601表示法，并使用UTC时间。\\n格式为：YYYY-MM-DDThh:mm:ssZ|
|400|InvalidEndTime.Malformed|The specified EndTime is invalid.|请提供正确的结束时间格式。日期格式按照ISO8601表示法，并使用UTC时间。 格式为：YYYY-MM-DDThh:mm:ssZ|
|400|InvalidEndTime.Mismatch|The specified EndTime is earlier than the StartTime.|结束时间早于开始时间，请检查。|
|400|InvalidStartTime.ValueNotSupported|The specified StartTime is invalid.|不支持该开始时间，请重新填写。|
|400|InvalidObjectType.ValueNotSupported|The specified ObjectType is not supported.|ObjectType错误，请重新填写ObjectType。|
|400|InvalidStatus.ValueNotSupported|The specified Status is not supported.|Status错误，请填写正确的Status。|
|400|DomainNameOverLimit|A maximum of 500 domains are supported for each request.|一次最多只支持500个域名，请减少域名重新请求。|

访问[错误中心](https://error-center.aliyun.com/status/product/dcdn)查看更多错误码。

