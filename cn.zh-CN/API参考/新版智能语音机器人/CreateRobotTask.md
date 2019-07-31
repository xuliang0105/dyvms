# CreateRobotTask {#doc_api_Dyvmsapi_CreateRobotTask .reference}

调用接口CreateRobotTask发起智能语音机器人外呼任务。

在智能语音交互通话中，支持使用控制台预设的机器人话术，或在每轮通话中通过回调接口返回业务方设置的回应方式。

接口**CreateRobotTask**用于直接使用控制台预设的机器人话术，发起机器人外呼任务。

调用该接口前，请确认：

-   已实名认证为企业用户，并审核通过了企业资质。
-   已在[语音服务控制台](https://dyvms.console.aliyun.com/dyvms.htm#/number/normal) 上购买了号码。
-   已在[话术管理页面](https://dyvms.console.aliyun.com/dyvms.htm#/smart-call/saas/robot/list)添加了话术并通过审核。

**说明：** 请确保在使用该接口前，已充分了解语音服务产品的收费方式和[价格](https://www.aliyun.com/price/product#/vms/detail)。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Dyvmsapi&api=CreateRobotTask&type=RPC&version=2017-05-25)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|AccessKeyId|String|否|LTAIP00vvvvvvvvv|主账号AccessKey的ID。

 |
|Action|String|否|CreateRobotTask|系统规定参数。取值：**CreateRobotTask**。

 |
|Caller|String|否|13700000000|被叫号码。仅支持中国大陆号码。

 支持设置1~1000个被叫号码，号码之间使用英文逗号（,）分隔。

 |
|CorpName|String|否|阿里巴巴通信技术\(北京\)有限公司|公司名称，和[资质管理页面](https://dyvms.console.aliyun.com/dyvms.htm#/corp/normal)中的**公司名称**完全一致，该参数为可选。

 |
|DialogId|Long|否|1234567|指定机器人ID，即话术ID。表示选择哪个机器人/话术发起呼叫。

 请在[话术管理页面](https://dyvms.console.aliyun.com/dyvms.htm#/smart-call/saas/robot/list)中查看**话术ID**。

 |
|IsSelfLine|Boolean|否|false|是否调用自有线路，默认为false。

 |
|NumberStatusIdent|Boolean|否|true|号码状态\(早媒体\)识别标识。默认为fasle，如果需要启用早媒体语音识别标识，请设置为true。

 |
|RecallInterval|Integer|否|5|重拨间隔，单位为分钟，必须大于1。

 |
|RecallStateCodes|String|否|200010,200011|需要重拨的通话状态，200010为关机，200011为停机， 200002为占线， 200012为呼损，200005为无法接通。

 |
|RecallTimes|Integer|否|1|重拨次数。

 |
|RetryType|Integer|否|1|是否自动重拨，1位重拨，0为不重拨。

 |
|TaskName|String|否|批量任务测试|任务名称。支持中文和英文，0~30个字符。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|请求状态码。

 -   返回OK代表请求成功。
-   其他错误码详见[错误码列表](~~112502~~)。

 |
|Data|String|4001112222|机器人呼叫任务的唯一任务ID，可以通过此ID调用接口查询任务详情。

 |
|Message|String|OK|状态码的描述。

 |
|RequestId|String|D9CB3933-9FE3-4870-BA8E-2BEE91B69D23|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=CreateRobotTask
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreateRobotTaskResponse>
	  <Message>OK</Message>
	  <RequestId>D9CB3933-9FE3-4870-BA8E-2BEE91B69D23</RequestId>
	  <Code>OK</Code>
	  <Data>4001112222</Data>
</CreateRobotTaskResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Data":"4001112222",
	"Message":"OK",
	"RequestId":"D9CB3933-9FE3-4870-BA8E-2BEE91B69D23",
	"Code":"OK"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Dyvmsapi)查看更多错误码。

