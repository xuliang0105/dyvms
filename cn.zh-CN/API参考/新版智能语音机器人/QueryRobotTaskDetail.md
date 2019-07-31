# QueryRobotTaskDetail {#doc_api_Dyvmsapi_QueryRobotTaskDetail .reference}

调用QueryRobotTaskDetail获取智能语音任务详情。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Dyvmsapi&api=QueryRobotTaskDetail&type=RPC&version=2017-05-25)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|AccessKeyId|String|否|LTAIP00vvvvvvvvv|主账号AccessKey的ID。

 |
|Action|String|否|QueryRobotTaskDetail|系统规定参数。取值：**QueryRobotTaskDetail**。

 |
|Id|Long|否|1045001|机器人呼叫任务的唯一任务ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|请求状态码。

 -   返回OK代表请求成功。
-   其他错误码详见[错误码列表](~~112502~~)。

 |
|Data|String|\{"id":1045001,"taskName":"智能语音务","robotId":1000000075003,"robotName":"机器人","corpName":"广东合富房地产置业有限公司1,广东合富房地产置业有限公司2 ","caller":"057156860008,057156860006", "numberStatusIdent":true,"status":"INIT","scheduleType":"SINGLE", "retryType":1,"recallStateCodes":"200010,200011", "recallTimes":2,"recallInterval":5,"createTime": "2019-06-14 11:04:19","fireTime":"2019-06-14 11:05:23","completeTime": "2019-06-14 18:21:06","called": \[\{"fileName": "5102636f-7be6-4a2d-9ac7-755a2e140a50--robotCallApi", "ossFilePath": "http://alicom-fc-media.cn-hangzhou.oss.aliyun-inc.com/5102636f-7be6-4a2d-9ac7-755a2e140a50--robotCallApi.xlsx"\}\]\}|Id：机器人呼叫任务的唯一任务ID。

 taskName：任务名称。

 robotId：指定机器人ID。

 robotName：机器人名称。

 corpName：公司名称。

 caller：被叫显号。

 numberStatusIdent：号码状态识别，true为识别，false为不识别。

 status：任务状态，INIT为初始，READY为开始任务，DISPATCH为解析中，EXCUTING为执行中，MANUAL\_STOP为手工暂停，SYSTEM\_STOP为系统暂停，ARREARS\_STOP为欠费暂停，CANCEL为终止，FINISH为完成。

 scheduleType：调度类型，SINGLE为立即启动，ORDER为定时启动。

 retryType：是否自动重拨，1位重拨，0为不重拨。

 recallStateCodes：需要重拨的通话状态，200010为关机，200011为停机， 200002为占线， 200012为呼损，200005为无法接通。

 recallTimes：重拨次数。

 recallInterval：重拨间隔，单位为分钟。

 createTime：任务创建时间。

 fireTime: 任务启动时间。

 completeTime: 任务完成时间。

 filename：被叫号码文件名。

 ossFilePath：被叫号码文件地址。

 |
|Message|String|OK|状态码的描述。

 |
|RequestId|String|D9CB3933-9FE3-4870-BA8E-2BEE91B69D23|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=QueryRobotTaskDetail
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<QueryRobotTaskDetailResponse>
	  <Message>OK</Message>
	  <RequestId>D9CB3933-9FE3-4870-BA8E-2BEE91B69D23</RequestId>
	  <Code>OK</Code>
	  <Data>{"id":1045001,"taskName":"智能语音务","robotId":1000000075003,"robotName":"机器人","corpName":"广东合富房地产置业有限公司1,广东合富房地产置业有限公司2 ","caller":"057156860008,057156860006", "numberStatusIdent":true,"status":"INIT","scheduleType":"SINGLE", "retryType":1,"recallStateCodes":"200010,200011", "recallTimes":2,"recallInterval":5,"createTime": "2019-06-14 11:04:19","fireTime":"2019-06-14 11:05:23","completeTime": "2019-06-14 18:21:06","called": [{"fileName": "5102636f-7be6-4a2d-9ac7-755a2e140a50--robotCallApi", "ossFilePath": "http://alicom-fc-media.cn-hangzhou.oss.aliyun-inc.com/5102636f-7be6-4a2d-9ac7-755a2e140a50--robotCallApi.xlsx"}]}</Data>
</QueryRobotTaskDetailResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Data":{
		"caller":"057156860008,057156860006",
		"createTime":"2019-06-14 11:04:19",
		"status":"INIT",
		"retryType":1,
		"taskName":"智能语音务",
		"robotName":"机器人",
		"id":1045001,
		"numberStatusIdent":true,
		"scheduleType":"SINGLE",
		"corpName":"广东合富房地产置业有限公司1,广东合富房地产置业有限公司2 ",
		"recallTimes":2,
		"fireTime":"2019-06-14 11:05:23",
		"robotId":1000000075003,
		"called":[
			{
				"ossFilePath":"http://alicom-fc-media.cn-hangzhou.oss.aliyun-inc.com/5102636f-7be6-4a2d-9ac7-755a2e140a50--robotCallApi.xlsx",
				"fileName":"5102636f-7be6-4a2d-9ac7-755a2e140a50--robotCallApi"
			}
		],
		"recallInterval":5,
		"recallStateCodes":"200010,200011",
		"completeTime":"2019-06-14 18:21:06"
	},
	"Message":"OK",
	"RequestId":"D9CB3933-9FE3-4870-BA8E-2BEE91B69D23",
	"Code":"OK"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Dyvmsapi)查看更多错误码。

