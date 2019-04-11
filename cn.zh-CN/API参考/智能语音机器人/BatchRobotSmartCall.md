# BatchRobotSmartCall {#doc_api_Dyvmsapi_BatchRobotSmartCall .reference}

调用接口BatchRobotSmartCall发起机器人外呼任务。

在智能语音交互通话中，支持使用控制台预设的机器人话术，或在每轮通话中通过回调接口返回业务方设置的回应方式。

接口**BatchRobotSmartCall**用于直接使用控制台预设的机器人话术，发起机器人外呼任务。

调用该接口前，请确认：

-   已实名认证为企业用户，并审核通过了企业资质。
-   已在[语音服务控制台](https://dyvms.console.aliyun.com/dyvms.htm#/number/normal)上购买了号码。
-   已在[话术管理页面](https://dyvms.console.aliyun.com/dyvms.htm#/smart-call/saas/robot/list)添加了话术并通过审核。

**说明：** 请确保在使用该接口前，已充分了解语音服务产品的收费方式和[价格](https://www.aliyun.com/price/product#/vms/detail)。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Dyvmsapi&api=BatchRobotSmartCall)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CalledNumber|String|是|13700000000|被叫号码。仅支持中国大陆号码。

 |
|CalledShowNumber|String|是|4001112222|被叫显号，必须是已购买的号码。

 您可以在[语音服务控制台](https://dyvms.console.aliyun.com/dyvms.htm#/number/normal)上查看已购买的号码。

 |
|DialogId|String|是|1234567|指定机器人ID，即话术ID。表示选择哪个机器人/话术发起呼叫。

 请在[话术管理页面](https://dyvms.console.aliyun.com/dyvms.htm#/smart-call/saas/robot/list)中查看**话术ID**。

 |
|TaskName|String|是|批量任务测试|任务名称。支持中文和英文，0~30个字符。

 |
|AccessKeyId|String|否|LTAIP00vvvvvvvvv|主账号AccessKey的ID。

 |
|Action|String|否|BatchRobotSmartCall|系统规定参数。取值：**BatchRobotSmartCall**。

 |
|CorpName|String|否|阿里巴巴通信技术\(北京\)有限公司|公司名称，必须和[资质管理页面](https://dyvms.console.aliyun.com/dyvms.htm#/corp/normal)中的**公司名称**完全一致。

 **说明：** 如果开通了**自有线路**功能，即**isSelfLine**为**true**时，该参数为可选。反之则必须填写公司名称。

 |
|EarlyMediaAsr|Boolean|否|true|早媒体语音识别标识。默认为fasle，如果需要启用早媒体语音识别标识，请设置为true。

 |
|IsSelfLine|Boolean|否|true|是否调用自有线路，默认为false。

 |
|ScheduleCall|Boolean|否|true|是否定时呼叫。如果设置为true，则必须设置**ScheduleTime**。

 |
|ScheduleTime|Long|否|1554110977000|预设的呼叫时间。Unix时间戳格式，单位为毫秒。

 **说明：** 当参数**ScheduleCall**为true时必选。

 |
|TtsParam|String|否|\[\{“number”:”13700000000”,”params”:\[“小王”,”小李”,”小周”\]\}\]|TTS模板的变量值，格式为JSON。

 必须和具体的号码对应、TtsParam和上面的TtsParamHead变量名称一一对应。

 |
|TtsParamHead|String|否|\[“name1”,”name2”,”name3”\]|带变量的呼叫任务，格式为JSON。变量名称列表，和下面的ttsParam配合使用

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|请求状态码。

 -   返回OK代表请求成功。
-   其他错误码详见[错误码列表](~~112502~~)。

 |
|Message|String|OK|状态码的描述。

 |
|RequestId|String|D9CB3933-9FE3-4870-BA8E-2BEE91B69D23|请求ID。

 |
|TaskId|String|4001112222|机器人呼叫任务的唯一任务ID，可以通过此ID调用接口**QueryCallDetailByTaskId**查询任务详情。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?CalledNumber=13700000000
&CalledShowNumber=4001112222
&DialogId=1234567
&TaskName=批量任务测试	
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<BatchRobotSmartCallResponse>
  <Message>OK</Message>
  <RequestId>D9CB3933-9FE3-4870-BA8E-2BEE91B69D23</RequestId>
  <Code>OK</Code>
  <TaskId>4001112222</TaskId>
</BatchRobotSmartCallResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"OK",
	"RequestId":"D9CB3933-9FE3-4870-BA8E-2BEE91B69D23",
	"TaskId":"4001112222",
	"Code":"OK"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Dyvmsapi)

