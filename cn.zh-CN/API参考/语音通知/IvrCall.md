# IvrCall {#doc_api_Dyvmsapi_IvrCall .reference}

调用接口IvrCall发起交互式语音通话。

接口**IvrCall**用于发起交互式语音通话。用户接听到电话后，播放一段语音，提示用户按键进行选择，如果开启了[消息回执](~~112503~~)，语音平台会返回客户按键信息给调用的业务系统。该接口可用于收集客户的订单确认、问卷调查、满意度调查等信息。

调用该接口前，请确认：

-   已实名认证为企业用户，并审核通过了企业资质。
-   已在[语音服务控制台](https://dyvms.console.aliyun.com/dyvms.htm#/number/normal)上购买了号码。
-   已在[语音文件页面](https://dyvms.console.aliyun.com/dyvms.htm#/file/notify)上传了语音文件，或在[文本转语音模板页面](https://dyvms.console.aliyun.com/dyvms.htm#/template)创建了文本转语音（TTS）模板，语音文件和文本转语音模板都必须经过审核。

**说明：** 请确保在使用该接口前，已充分了解语音服务产品的收费方式和[价格](https://www.aliyun.com/price/product#/vms/detail)。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Dyvmsapi&api=IvrCall&type=RPC&version=2017-05-25)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CalledNumber|String|是|13700000000|被叫号码。仅支持中国大陆号码。

 |
|CalledShowNumber|String|是|4001112222|被叫显号，必须是已购买的号码。

 您可以在[语音服务控制台](https://dyvms.console.aliyun.com/dyvms.htm#/number/normal)上查看已购买的号码。

 |
|StartCode|String|是|TTS\_1234|呼叫开始时播放的提示音，可以指定为：

 -   **语音文件**：语音ID。可以在[文本转语音模板页面](https://dyvms.console.aliyun.com/dyvms.htm#/file/notify)查看语音ID。
-   **文本转语音模板**：模板ID。可以在[文本转语音模板页面](https://dyvms.console.aliyun.com/dyvms.htm#/template)查看模板ID。

 |
|AccessKeyId|String|否|LTAIP00vvvvvvvvv|主账号AccessKey的ID。

 |
|Action|String|否|IvrCall|系统规定参数。取值：**IvrCall**。

 |
|ByeCode|String|否|TTS\_1234|播放结束时播放的结束提示音，支持以下两种方式：

 -   语音文件
-   文本转语音（TTS）模板

 **说明：** 参数**ByeCode**的类型需要与参数**StartCode**一致，即必须同时为语音文件或文本转语音（TTS）模板。

 |
|ByeTtsParams|String|否|\{“name”:”xxx”,”code”:”123”\}|文本转语音模板变量替换关系，格式为JSON。

 **说明：** 当**ByeCode**为文本转语音（TTS）模板、且模板中带变量的情况下此参数为必选。

 |
|MenuKeyMap.N.Code|String|否|TTS\_1234|**MenuKeyMap.N.Key**中指定的按键对应的提示音。支持以下两种方式：

 -   语音文件
-   文本转语音（TTS）模板

 |
|MenuKeyMap.N.Key|String|否|1|被叫方可按的电话按键。

 |
|MenuKeyMap.N.TtsParams|String|否|\{“name”:”xxx”,”code”:”123”\}|**MenuKeyMap.N.Code**是文本转语音模板（TTS）时，对应的模板变量替换关系，格式为JSON。

 **说明：** 当**MenuKeyMap.N.Code**为文本转语音模板（TTS）、且模板中带变量的情况下此参数为必选。

 |
|OutId|String|否|abcdefgh|预留给调用方使用的ID，最终会通过在回执消息中将此ID带回给调用方。

 |
|PlayTimes|Long|否|3|重复播放次数，取值范围为1~3。

 |
|StartTtsParams|String|否|\{“name”:”xxx”,”code”:”123”\}|文本转语音模板（TTS）变量替换关系，格式为JSON。

 **说明：** 当**StartCode**为文本转语音模板（TTS）、且模板中带变量的情况下此参数为必选。

 |
|Timeout|Integer|否|3000|等待用户按键超时时间，单位为毫秒。

 |

## 返回数据 {#resultMapping .section}

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
&StartCode=TTS_1234
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<IvrCallResponse>
	  <Message>OK</Message>
	  <RequestId>D9CB3933-9FE3-4870-BA8E-2BEE91B69D23</RequestId>
	  <Code>OK</Code>
	  <CallId>116012354148^102813784148</CallId>
</IvrCallResponse>
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

访问[错误中心](https://error-center.aliyun.com/status/product/Dyvmsapi)查看更多错误码。

