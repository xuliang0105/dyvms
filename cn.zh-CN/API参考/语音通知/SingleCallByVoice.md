# SingleCallByVoice {#doc_api_Dyvmsapi_SingleCallByVoice .reference}

调用接口SingleCallByVoice发起语音文件类型的语音通知。

接口**SingleCallByVoice**用于向指定号码发起语音文件类型的语音通知。

调用该接口前，请确认：

-   已实名认证为企业用户，并审核通过了企业资质。
-   已在[语音服务控制台](https://dyvms.console.aliyun.com/dyvms.htm#/number/normal)上购买了号码。
-   已在[语音文件页面](https://dyvms.console.aliyun.com/dyvms.htm#/file/notify)上传了语音文件，并通过了审核。

**说明：** 请确保在使用该接口前，已充分了解语音服务产品的收费方式和[价格](https://www.aliyun.com/price/product#/vms/detail)。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Dyvmsapi&api=SingleCallByVoice&type=RPC&version=2017-05-25)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CalledNumber|String|是|13700000000|被叫号码。仅支持中国大陆号码。

 |
|CalledShowNumber|String|是|4001112222|被叫显号，必须是已购买的号码。

 您可以在[语音服务控制台](https://dyvms.console.aliyun.com/dyvms.htm#/number/normal)上查看已购买的号码。

 |
|VoiceCode|String|是|2d4c-4e78-8d2a-afbb06cf6216.wav|语音文件的语音ID，可以在[文本转语音模板页面](https://dyvms.console.aliyun.com/dyvms.htm#/file/notify)查看语音ID。

 |
|AccessKeyId|String|否|LTAIP00vvvvvvvvv|主账号AccessKey的ID。

 |
|Action|String|否|SingleCallByVoice|系统规定参数。取值：**SingleCallByVoice**。

 |
|OutId|String|否|abcdefgh|预留给调用方使用的ID, 最终会通过在回执消息中将此ID带回给调用方。

 字符串类型，长度为1~15个字节。

 |
|PlayTimes|Integer|否|3|语音文件的播放次数，取值范围为1~3。

 |
|Speed|Integer|否|100|**说明：** 该参数为废弃参数，暂不支持使用。

 |
|Volume|Integer|否|100|语音文件播放的音量。取值范围为0~100，默认为100。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|CallId|String|116004767703^102806207703|此次通话的唯一回执ID，可以用此ID通过接口**QueryCallDetailByCallId**查询呼叫详情。

 |
|Code|String|OK|请求状态码。

 -   返回OK代表请求成功。
-   其他错误码详见[错误码列表](~~112502~~)。

 |
|Message|String|OK|状态码的描述。

 |
|RequestId|String|E50FFA85-0B79-4421-A7BD-00B0A271966F|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?CalledNumber=13700000000
&CalledShowNumber=4001112222
&VoiceCode=2d4c-4e78-8d2a-afbb06cf6216.wav
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<SingleCallByVoiceResponse>
	  <Message>OK</Message>
	  <RequestId>E50FFA85-0B79-4421-A7BD-00B0A271966F</RequestId>
	  <Code>OK</Code>
	  <CallId>116004767703^102806207703</CallId>
</SingleCallByVoiceResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"OK",
	"RequestId":"E50FFA85-0B79-4421-A7BD-00B0A271966F",
	"Code":"OK",
	"CallId":"116004767703^102806207703"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Dyvmsapi)查看更多错误码。

