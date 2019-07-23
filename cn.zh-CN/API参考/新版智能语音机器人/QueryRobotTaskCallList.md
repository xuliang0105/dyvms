# QueryRobotTaskCallList {#doc_api_Dyvmsapi_QueryRobotTaskCallList .reference}

查询智能语音任务通话列表

查询智能语音任务通话列表

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Dyvmsapi&api=QueryRobotTaskCallList)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|AccessKeyId|String|否|LTAIP00vvvvvvvvv|主账号AccessKey的ID。

 |
|Action|String|否|QueryRobotTaskCallList|系统规定参数。取值：**QueryRobotTaskCallList**。

 |
|CallResult|String|否|200002|通话结果， 200002-占线，200005-无法接通，200010-关机，200011-停机，200012-呼损。

 |
|Called|String|否|1300000000|被叫号码。

 |
|DialogCountFrom|String|否|0|对话轮次，左边数值。

 |
|DialogCountTo|String|否|5|对话轮次，右边数值。

 |
|DurationFrom|String|否|0|通话时长，左边数值。

 |
|DurationTo|String|否|60|通话时长，右边数值。

 |
|HangupDirection|String|否|1|挂断方向，0-用户，1-机器人。

 |
|PageNo|Integer|否|1|分页参数，当前页数

 |
|PageSize|Integer|否|20|分页参数，每页记录数

 |
|TaskId|String|否|1045001|机器人呼叫任务的唯一任务ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|请求状态码。

 -   返回OK代表请求成功。
-   其他错误码详见[错误码列表](~~112502~~)。

 |
|Data|String|\[ \{ “taskId” : 1045001， “caller” : “0571-88996676”, “called” : “13000000000”, “duration” : “60”, “label” : “邀约，有房，无车”, “dialogCount” : “3”, “callResult” : “无法接通”, “hangupDirection” : “1”, “transferResult“ : “3”, “transferNumber” ：0571-88336676, “transferFailReason” ：“用户挂断”, “callId” ：“116950320375^103750100375”, “recallCurTimes” : 2, “callStartTime” : “2019.06.14 15:22:23”, “callEndTime” : “2019.06.14 15:22:55”, “sureCount” : 2, “denyCount” : 2, “rejectCount” : 0, “customCount” : 0, “konwledgeCount” : 0, “defaultCount” : 0, “knowledgeBusinessCount” : 0, “knowledgeCommonCount” : 0 \} \]|智能语音任务通话列表，JSON数组格式。参数包括：

 • taskId ：机器人呼叫任务的唯一任务ID。

 • caller ：主叫号码。

 called ：被叫号码。

 duration ：通话时长（秒）。

 label ：标签。

 dialogCount ：对话轮次。

 callResult ：通话结果。

 hangupDirection ：挂断方向，0-用户，1-机器人。

 transferResult ：转接人工状态，1-转接成功，0-转接失败，3-未转人工。

 transferNumber ：人工座席号码。

 transferFailReson ：转接人工失败原因。

 callId ：callId，taskId+^+bizId。

 recallCurTimes ：重试次数。

 callStartTime ：通话开始时间。

 callEndTime ：通话结束时间。

 sureCount ：肯定次数。

 denyCount ：否定次数。

 rejectCount ：拒绝次数。

 customCount ：自定义次数。

 konwledgeCount ：知识库次数。

 defaultCount ：默认次数。

 knowledgeBusinessCount ：业务问题次数。

 knowledgeCommonCount ：通用问题次数。

 |
|Message|String|OK|状态码的描述。

 |
|RequestId|String|D9CB3933-9FE3-4870-BA8E-2BEE91B69D23|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=QueryRobotTaskCallList
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<QueryRobotTaskCallListResponse>
  <Message>OK</Message>
  <RequestId>D9CB3933-9FE3-4870-BA8E-2BEE91B69D23</RequestId>
  <Code>OK</Code>
  <Data>[ { "taskId": 1045001, "caller": "0571-88996676", "called": "13000000000", "duration": "60", "label": "邀约,有房,无车", "dialogCount": "3", "callResult": "无法接通", "hangupDirection": "1", "transferResult": "3", "transferNumber":"0571-88336676", "transferFailReason" :"用户挂断", "callId" :"116950320375^103750100375", "recallCurTimes": 2, "callStartTime": "2019.06.14 15:22:23", "callEndTime": "2019.06.14 15:22:55", "sureCount": 2, "denyCount": 2, "rejectCount": 0, "customCount": 0, "konwledgeCount": 0, "defaultCount": 0, "knowledgeBusinessCount": 0, "knowledgeCommonCount": 0 } ]</Data>
</QueryRobotTaskCallListResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Data":[
		{
			"rejectCount":0,
			"taskId":1045001,
			"caller":"0571-88996676",
			"dialogCount":"3",
			"recallCurTimes":2,
			"sureCount":2,
			"transferResult":"3",
			"transferNumber":"0571-88336676",
			"defaultCount":0,
			"label":"邀约,有房,无车",
			"customCount":0,
			"callStartTime":"2019.06.14 15:22:23",
			"callId":"116950320375^103750100375",
			"konwledgeCount":0,
			"denyCount":2,
			"callEndTime":"2019.06.14 15:22:55",
			"duration":"60",
			"knowledgeCommonCount":0,
			"transferFailReason":"用户挂断",
			"called":"13000000000",
			"callResult":"无法接通",
			"knowledgeBusinessCount":0,
			"hangupDirection":"1"
		}
	],
	"Message":"OK",
	"RequestId":"D9CB3933-9FE3-4870-BA8E-2BEE91B69D23",
	"Code":"OK"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Dyvmsapi)查看更多错误码。

