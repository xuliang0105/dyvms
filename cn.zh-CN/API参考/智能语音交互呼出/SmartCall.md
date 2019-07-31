# SmartCall {#doc_api_Dyvmsapi_SmartCall .reference}

调用接口SmartCall发起智能语音交互通话。

在智能语音交互通话中，支持使用控制台预设的机器人话术，或在每轮通话中通过回调接口返回业务方设置的回应方式。

接口**SmartCall**需要和[智能外呼回调HTTP接口](~~112703~~)联合使用，语音平台发起呼叫后，会把转换后的语音文本回传给业务方，业务方把下一步的执行动作返回给语音平台。

调用该接口前，请确认：

-   已实名认证为企业用户，并审核通过了企业资质。
-   已在[语音服务控制台](https://dyvms.console.aliyun.com/dyvms.htm#/number/normal)上购买了号码。
-   已在[服务开通页面](https://dyvms.console.aliyun.com/dyvms.htm#/generalSetting/open)开通**智能外呼ASR**，并在[订阅回执消息页面](https://dyvms.console.aliyun.com/dyvms.htm#/generalSetting/mns)开启**智能外呼ASR实时交互**。详细说明请参考[回调接口说明](~~112701~~)和[智能外呼回调HTTP接口](~~112703~~)。

**说明：** 请确保在使用该接口前，已充分了解语音服务产品的收费方式和[价格](https://www.aliyun.com/price/product#/vms/detail)。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Dyvmsapi&api=SmartCall&type=RPC&version=2017-05-25)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CalledNumber|String|是|13700000000|被叫号码。仅支持中国大陆号码。

 |
|CalledShowNumber|String|是|4001112222|被叫显号，必须是已购买的号码。

 您可以在[语音服务控制台](https://dyvms.console.aliyun.com/dyvms.htm#/number/normal)上查看已购买的号码。

 |
|VoiceCode|String|是|2d4c-4e78-8d2a-afbb06cf6216.wav,$name$|智能外呼放音文件，支持网络文件、控制台上传的语音文件和TTS三种方式。其中，支持使用多个文件和TTS参数混播，之间用逗号分隔。TTS参数的替换值在**VoiceCodeParam**中指定。

 -   放音文件为网络文件时：参数**VoiceCode**指定为可被公网访问的语音文件URL。
-   放音文件为控制台上传的语音文件时：参数**VoiceCode**指定为文件的语音ID。可以在[智能外呼放音文件](https://dyvms.console.aliyun.com/dyvms.htm#/file/smartcall)中单击进入文件详情，查看智能外呼放音文件的**语音ID**。
-   放音文件为TTS时：参数**VoiceCode**指定为文本转语音（TTS）模板的模板ID。可以在[文本转语音模板](https://dyvms.console.aliyun.com/dyvms.htm#/template)中查看**模板ID**。

 **说明：** 如需将放音文件设置为网络文件或TTS，请先[提交云工单](https://selfservice.console.aliyun.com/ticket/category/dyvms/today)联系小二开通。

 |
|Action|String|否|SmartCall|系统规定参数。取值：**SmartCall**。

 |
|VoiceCodeParam|String|否|“\{\\”name\\”:\\”喂，你好\\”\}”|TTS参数传递字符串，格式为JSON。

 **说明：** 必须与**VoiceCode**的TTS参数对应。

 |
|RecordFlag|Boolean|否|true|通话过程中是否录音。

 |
|Volume|Integer|否|1|播放音频的音量，取值范围为-4~4，建议设置为1。

 |
|Speed|Integer|否|1|**说明：** 该参数为废弃参数，暂不支持使用。

 |
|AsrModelId|String|否|155780923770|ASR模型ID。请在[ASR模型管理页面](https://dyvms.console.aliyun.com/dyvms.htm#/smart-call/asr/1)查看ASR模型ID。

 |
|AccessKeyId|String|否|LTAIP00vvvvvvvvv|主账号AccessKey的ID。

 |
|MuteTime|Integer|否|10000|静音时长，单位为ms，取值范围为1000~20000，如果指定值不在参数范围中，则默认**MuteTime**为10000。

 |
|ActionCodeBreak|Boolean|否|true|开场放音文件是否可打断。默认为true，即开场放音文件可打断。

 |
|OutId|String|否|abcdefgh|预留给调用方使用的ID, 最终会通过在回执消息中将此ID带回给调用方。

 字符串类型，长度为1~15个字节。

 |
|DynamicId|String|否|abcdefgh|预留给调用方使用的动态扩展ID，在回调地址中带回，用于客户的开发标识。

 |
|EarlyMediaAsr|Boolean|否|true|早媒体语音识别标识。默认为fasle，即关闭状态，如果需要启用早媒体语音识别标识，请手动设为true。

 |
|PauseTime|Integer|否|800|停顿时长，单位为毫秒。取值范围为300~1200，如果指定值不在参数范围中，则默认**PauseTime**为800。

 |
|SessionTimeout|Integer|否|120|最大通话时长，单位为秒，超时后自动挂断。

 |
|ActionCodeTimeBreak|Integer|否|120|基于用户持续说话时长打断，在AtionCodeBreak为true时生效。单位为毫秒。

 **说明：** **ActionCodeTimeBreak**取值必须大于0。

 |
|TtsStyle|String|否|xiaoyun|TTS变量播放时的声音风格，默认为**xiaoyan**，具体风格见声音风格列表。

 |
|TtsVolume|Integer|否|10|TTS变量播放的音量，取值范围为0~100，默认为0。

 |
|TtsSpeed|Integer|否|100|TTS变量播放时的声音速度，取值范围为-200~200，默认为0。

 |
|TtsConf|Boolean|否|true|是否设置TTS声音参数。

 -   指定为**true**：需要通过**TtsStyle**、**TtsColume**、**TtsSpeed**三个参数来设置声音风格。
-   指定为**false**：不需要设置相关参数，即便设置了也不生效。

 |
|AsrBaseId|String|否|customer\_service\_8k|ASR基础模型。可设置为：

 -   **customer\_service\_8k**：普通话。
-   **dialect\_customer\_service\_8k**：重口音。

 **注意**：

 调用接口**SmartCall**时，需要指定使用的ASR模型，建议参数**asrModelId**和**AsrBaseId**二者选填一个。

 -   如果仅设置**asrModelId**，表示使用指定的ASR模型。
-   如果仅设置**AsrBaseId**，表示使用指定的ASR基础模型。
-   如果二者均未设置，则使用默认的ASR基础模型，即参数**AsrBaseId**默认为**customer\_service\_8k**，表示使用ASR普通话基础模型。
-   如果二者同时设置，请确认二者是正确对应的。

 |

## 声音风格列表 {#requestParamsSupplement .section}

|说明

|编码

|
|----|----|
|小云标准女声

|xiaoyun

|
|小刚标准男声

|xiaogang

|
|若兮温柔女声

|ruoxi

|
|小梦标准女声

|xiaomeng

|
|小威标准男声

|xiaowei

|
|阿美甜美女声

|amei

|
|小雪温柔女声

|xiaoxue

|
|思琪温柔女声

|siqi

|
|思佳标准女声

|sijia

|
|思诚标准男声

|sicheng

|
|思悦温柔女声

|siyue

|
|小美甜美女声

|xiaomei

|
|思彤标准童声

|sitong

|
|宁儿标准女声

|ninger

|
|小北萝莉女声

|xiaobei

|
|伊娜浙普女声

|yina

|

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|CallId|String|116012854210^102814279210|此次通话的唯一回执ID，可以用此ID通过接口**QueryCallDetailByCallId**查询呼叫详情。

 |
|Code|String|OK|请求状态码。

 -   返回OK代表请求成功。
-   其他错误码详见[错误码列表](~~112502~~)。

 |
|Message|String|OK|状态码的描述。

 |
|RequestId|String|A90E4451-FED7-49D2-87C8-00700A8C4D0D|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=SmartCall
&CalledNumber=13700000000
&CalledShowNumber=4001112222
&VoiceCode=2d4c-4e78-8d2a-afbb06cf6216.wav,$name$
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<SmartCallResponse>
	  <Message>OK</Message>
	  <RequestId>A90E4451-FED7-49D2-87C8-00700A8C4D0D</RequestId>
	  <Code>OK</Code>
	  <CallId>116012854210^102814279210</CallId>
</SmartCallResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"OK",
	"RequestId":"A90E4451-FED7-49D2-87C8-00700A8C4D0D",
	"Code":"OK",
	"CallId":"116012854210^102814279210"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Dyvmsapi)查看更多错误码。

