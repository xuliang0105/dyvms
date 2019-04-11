# ClickToDial {#doc_api_Dyvmsapi_ClickToDial .reference}

调用接口ClickToDial发起一次双方通话。

接口**ClickToDial**用于发起一次双方通话。调用成功后，语音服务使用主叫显号打给主叫号码，然后使用被叫显号打给被叫号码，为主叫和被叫号码双方发起一次语音通信。语音通信过程中，通话双方显示的号码均为语音服务平台号码。

该接口可用于点击呼叫场景。

调用该接口前，请确认：

-   已实名认证为企业用户，并审核通过了企业资质。
-   已在[语音服务控制台](https://dyvms.console.aliyun.com/dyvms.htm#/number/normal)上购买了号码。

**说明：** 请确保在使用该接口前，已充分了解语音服务产品的收费方式和[价格](https://www.aliyun.com/price/product#/vms/detail)。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Dyvmsapi&api=ClickToDial)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CalledNumber|String|是|13700000001|被叫号码。仅支持中国大陆号码。

 |
|CalledShowNumber|String|是|4001112222|被叫显号，必须是已购买的号码。

 您可以在[语音服务控制台](https://dyvms.console.aliyun.com/dyvms.htm#/number/normal)上查看已购买的号码。

 |
|CallerNumber|String|是|13700000000|主叫号码。仅支持中国大陆号码。

 |
|CallerShowNumber|String|是|4001112221|主叫显号，必须是已购买的号码。

 您可以在[语音服务控制台](https://dyvms.console.aliyun.com/dyvms.htm#/number/normal)上查看已购买的号码。

 |
|AccessKeyId|String|否|LTAIP00vvvvvvvvv|主账号AccessKey的ID。

 |
|Action|String|否|ClickToDial|系统规定参数。取值：**ClickToDial**。

 |
|AsrFlag|Boolean|否|true|是否开启实时ASR功能。

 |
|AsrModelId|String|否|2070aca1eff146f9a7bc826f1c3d4d33|ASR模型ID。请在[ASR模型管理页面](https://dyvms.console.aliyun.com/dyvms.htm#/smart-call/asr/1)查看ASR模型ID。

 |
|OutId|String|否|abcdefgh|预留给调用方使用的ID, 最终会通过在回执消息中将此ID带回给调用方。

 字符串类型，长度为1~15个字节。

 |
|RecordFlag|Boolean|否|true|通话过程是否录音。

 |
|SessionTimeout|Integer|否|100|整个通话的最长时长，单位为秒。超过该时长后系统自动挂断电话。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|CallId|String|116012354148^102813784148|此次通话的唯一回执ID，可以用此ID通过接口**QueryCallDetailByCallId**查询呼叫详情。

 |
|Code|String|OK|请求状态码。

 -   返回OK代表请求成功。
-   其他错误码详见[错误码列表](~~112502~~)。

 |
|Message|String|OK|状态码的描述。

 |
|RequestId|String|D9CB3933-9FE3-4870-BA8E-2BEE91B69D23|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?CalledShowNumber=4001112222
&CallerNumber=13700000000
&CallerShowNumber=4001112221
&CalledNumber=13700000001
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ClickToDialResponse>
  <Message>OK</Message>
  <RequestId>D9CB3933-9FE3-4870-BA8E-2BEE91B69D23</RequestId>
  <Code>OK</Code>
  <CallId>116012354148^102813784148</CallId>
</ClickToDialResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"OK",
	"RequestId":"D9CB3933-9FE3-4870-BA8E-2BEE91B69D23",
	"Code":"OK",
	"CallId":"116012354148^102813784148"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Dyvmsapi)

