# QueryRobotTaskList {#doc_api_Dyvmsapi_QueryRobotTaskList .reference}

获取智能语音任务详情

获取智能语音任务列表

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Dyvmsapi&api=QueryRobotTaskList)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|QueryRobotTaskList|系统规定参数。取值：**QueryRobotTaskList**。

 |
|AccessKeyId|String|否|LTAIP00vvvvvvvvv|主账号AccessKey的ID。

 |
|Time|String|否|2019-06-14|任务创建日期，yyyy-MM-dd格式。

 |
|Status|String|否|EXCUTING|任务状态，状态如下：INIT 未开始

 READY 准备开始

 DISPATCH 解析中

 EXCUTING 执行中

 MANUAL\_STOP 手动暂停

 SYSTEM\_STOP 系统暂停

 ARREARS\_STOP 欠费暂停

 CANCEL 手动终止

 SYSTEM\_CANCEL 系统终止

 FINISH 已完成

 |
|TaskName|String|否|任务测试|任务名称

 |
|PageSize|Integer|否|20|分页参数，每页个数

 |
|PageNo|Integer|否|1|分页参数，第几页

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|请求状态码。

 |
|Data|String|\[ \{“id”: 1045001, “taskName”: “智能语音任务”, “robotId”: 1000000075003, “robotName”: “机器人”, “status”: “INIT”, “scheduleType”: “SINGLE”, “createTime”: “2019.06.14 14:55:23”, “completeTime”: “2019.06.14 14:55:23”, “fireTime”: “2019.06.14 14:55:23”, “totalCount”: 1000, “finishCount”: 998\} \]|智能语音任务列表，JSON数组格式。参数包括：

 • id ：机器人呼叫任务的唯一任务ID。

 • taskName ：任务名称。

 • robotId ：指定机器人ID。

 • robotName ：机器人名称。

 status ：任务状态，初始 INIT，开始任务 READY，解析中 DISPATCH，执行中 EXCUTING，手工暂停 MANUAL\_STOP，系统暂停SYSTEM\_STOP，欠费暂停 ARREARS\_STOP，终止 CANCEL，完成 FINISH。

 scheduleType ：调度类型，SINGLE为立即启动，ORDER为定时启动。

 createTime ：任务创建时间，yyyy.MM.dd HH:mm:ss格式。

 completeTime ：任务完成时间，yyyy.MM.dd HH:mm:ss格式。

 fireTime ：任务启动时间，yyyy.MM.dd HH:mm:ss格式。

 totalCount ：处理通话总数。

 finishCount ：完成通话个数。

 |
|Message|String|OK|状态码的描述。

 |
|RequestId|String|D9CB3933-9FE3-4870-BA8E-2BEE91B69D23|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=QueryRobotTaskList
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<QueryRobotTaskListResponse>
  <Message>OK</Message>
  <RequestId>D9CB3933-9FE3-4870-BA8E-2BEE91B69D23</RequestId>
  <Code>OK</Code>
  <Data>[ {"id": 1045001, "taskName": "智能语音任务", "robotId": 1000000075003, "robotName": "机器人", "status": "INIT", "scheduleType": "SINGLE", "createTime":  "2019.06.14 14:55:23", "completeTime": "2019.06.14 14:55:23", "fireTime": "2019.06.14 14:55:23", "totalCount": 1000, "finishCount": 998} </Data>
</QueryRobotTaskListResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Data":[
		{
			"id":1045001,
			"createTime":"2019.06.14 14:55:23",
			"scheduleType":"SINGLE",
			"fireTime":"2019.06.14 14:55:23",
			"totalCount":1000,
			"status":"INIT",
			"robotId":1000000075003,
			"finishCount":998,
			"completeTime":"2019.06.14 14:55:23",
			"taskName":"智能语音任务",
			"robotName":"机器人"
		}
	],
	"Message":"OK",
	"RequestId":"D9CB3933-9FE3-4870-BA8E-2BEE91B69D23",
	"Code":"OK"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Dyvmsapi)查看更多错误码。

