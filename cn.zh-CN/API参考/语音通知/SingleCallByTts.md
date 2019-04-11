# SingleCallByTts {#doc_api_Dyvmsapi_SingleCallByTts .reference}

调用接口SingleCallByTts发起语音通知，播放的音频为文本转语音模板转换后的音频文件。

接口**SingleCallByTts**用于向指定号码发起语音通知，若播放的音频为文本模板（TTS），每次调用时从文本模板转化为音频文件。文本转语音模板中还可以设置变量，调用时替换变量即可。

调用该接口前，请确认：

-   已实名认证为企业用户，并审核通过了企业资质。
-   已在[语音服务控制台](https://dyvms.console.aliyun.com/dyvms.htm#/number/normal)上购买了号码。
-   已在[文本转语音模板页面](https://dyvms.console.aliyun.com/dyvms.htm#/template)上传了文本转语音模板，并通过了审核。

**说明：** 请确保在使用该接口前，已充分了解语音服务产品的收费方式和[价格](https://www.aliyun.com/price/product#/vms/detail)。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Dyvmsapi&api=SingleCallByTts)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CalledNumber|String|是|13700000000|被叫号码。仅支持中国大陆号码。

 |
|CalledShowNumber|String|是|4001112222|被叫显号，必须是已购买的号码。

 您可以在[语音服务控制台](https://dyvms.console.aliyun.com/dyvms.htm#/number/normal)上查看已购买的号码。

 |
|TtsCode|String|是|TTS\_10001|文本转语音（TTS）模板ID。可以在[文本转语音模板页面](https://dyvms.console.aliyun.com/dyvms.htm#/template)查看模板ID。

 **说明：** 必须是已审核通过的文本转语音模板。

 |
|AccessKeyId|String|否|LTAIP00vvvvvvvvv|主账号AccessKey的ID。

 |
|Action|String|否|SingleCallByTts|系统规定参数。取值：**SingleCallByTts**。

 |
|OutId|String|否|abcdefgh|预留给调用方使用的ID, 最终会通过在回执消息中将此ID带回给调用方。

 字符串类型，长度为1~15个字节。

 |
|PlayTimes|Integer|否|3|语音通知的播放次数，取值范围为1~3。

 |
|Speed|Integer|否|5|**说明：** 该参数为废弃参数，暂不支持使用。

 |
|TtsParam|String|否|\{“AckNum”:”123456”\}|文本转语音（TTS）模板变量转换关系，格式为JSON。

 |
|Volume|Integer|否|100|语音通知的播放音量。取值范围为0~100，默认为100。

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

http(s)://[Endpoint]/?CalledNumber=13700000000
&CalledShowNumber=4001112222
&TtsCode=TTS_10001
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<SingleCallByTtsResponse>
  <Message>OK</Message>
  <RequestId>D9CB3933-9FE3-4870-BA8E-2BEE91B69D23</RequestId>
  <Code>OK</Code>
  <CallId>116012354148^102813784148</CallId>
</SingleCallByTtsResponse>

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

