# QueryRobotTaskCallDetail {#doc_api_Dyvmsapi_QueryRobotTaskCallDetail .reference}

调用QueryRobotTaskCallDetail查询智能语音任务通话详情。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Dyvmsapi&api=QueryRobotTaskCallDetail&type=RPC&version=2017-05-25)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|QueryRobotTaskCallDetail|系统规定参数。取值：**QueryRobotTaskCallDetail**。

 |
|AccessKeyId|String|否|LTAIP00vvvvvvvvv|主账号AccessKey的ID。

 |
|TaskId|Long|否|1045001|机器人呼叫任务的唯一任务ID。

 |
|Callee|String|否|13000000000|被叫号码

 |
|QueryDate|Long|否|1562297550000|需要查询时间的时间戳。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|请求状态码。

 -   返回OK代表请求成功。
-   其他错误码详见[错误码列表](~~112502~~)。

 |
|Data|String|\{ “taskId” : 1045001， “caller” : “0571-88996676”, “called” : “13000000000”, “duration” : “60”, “label” : “邀约，有房，无车”, “dialogCount” : “3”, “callResult” : “无法接通”, “hangupDirection” : “1”, “transferResult“ : “3”, “transferNumber” ：0571-88336676, “transferFailReason” ：“用户挂断”, “callId” ：“116950320375^103750100375”, “recallCurTimes” : 2, “callStartTime” : “2019.06.14 15:22:23”, “callEndTime” : “2019.06.14 15:22:55”, “sureCount” : 2, “denyCount” : 2, “rejectCount” : 0, “customCount” : 0, “konwledgeCount” : 0, “defaultCount” : 0, “knowledgeBusinessCount” : 0, “knowledgeCommonCount” : 0, “recordStatus”:1, “recordFile”: "http://alicom-fc-record-biz.cn-hangzhou.oss.aliyun-inc.com/Freeswitch\_RU\_117074080001\_ccd71132-8256-4eb4-9217-884e1d87c0d4\_record.wav?Expires=1562740186&OSSAccessKeyId=bypFNbGJVk7\*\*\*\*&Signature=99losPmytVl%2BMH85noZGD\*\*\*\*\*\*”, "dialogDetail": \[\{"role": "robot","speakTime": "2019-06-19 20:44:17","content":"开场白"\}\] \}|智能语音任务通话详情，JSON格式。参数包括：

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

 recordStatus ：录音文件状态。其中：

 1：有录音文件。

 2：没有录音文件。

 recordFile ：录音文件下载地址

 dialogDetail ：对话明细，一个JSON数组。其中包括：

 role ：发言对象。

 content ：发言内容。

 speakTime ：发言时间。

 |
|Message|String|OK|状态码的描述。

 |
|RequestId|String|D9CB3933-9FE3-4870-BA8E-2BEE91B69D23|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=QueryRobotTaskCallDetail
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<QueryRobotTaskCallDetailResponse>
	  <Message>OK</Message>
	  <RequestId>D9CB3933-9FE3-4870-BA8E-2BEE91B69D23</RequestId>
	  <Code>OK</Code>
	  <Data>{ "taskId" :1045001, "caller" :"0571-88996676", "called" :"13000000000", "duration" :"60", "label" :"邀约,有房,无车", "dialogCount" :"3", "callResult" :"无法接通", "hangupDirection" :"1", "transferResult" :"3", "transferNumber":"0571-88336676", "transferFailReason" :"用户挂断", "callId" :"116950320375^103750100375", "recallCurTimes" :2, "callStartTime" :"2019.06.14 15:22:23", "callEndTime" :"2019.06.14 15:22:55", "sureCount" :2, "denyCount" :2, "rejectCount" :0, "customCount" :0, "konwledgeCount" :0, "defaultCount" :0, "knowledgeBusinessCount" :0, "knowledgeCommonCount" :0 }</Data>
</QueryRobotTaskCallDetailResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Data":{
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
	},
	"Message":"OK",
	"RequestId":"D9CB3933-9FE3-4870-BA8E-2BEE91B69D23",
	"Code":"OK"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Dyvmsapi)查看更多错误码。

