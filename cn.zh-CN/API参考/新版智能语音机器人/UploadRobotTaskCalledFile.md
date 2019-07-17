# UploadRobotTaskCalledFile {#doc_api_Dyvmsapi_UploadRobotTaskCalledFile .reference}

上传智能语音任务的被叫号码

在创建智能语音机器人任务后，需要分批上传被叫号码，每个任务最多上传30万个号码，可分多次上传完成。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Dyvmsapi&api=UploadRobotTaskCalledFile)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|AccessKeyId|String|否|LTAIP00vvvvvvvvv|主账号AccessKey的ID。

 |
|Action|String|否|UploadRobotTaskCalledFile|系统规定参数。取值：**UploadRobotTaskCalledFile**。

 |
|CalledNumber|String|否|13700000000, 13711111111|被叫号码，支持设置多个，号码之间使用英文逗号（,）分隔。

 |
|Id|Long|否|1045001|机器人呼叫任务的唯一任务ID。

 |
|TtsParam|String|否|\[\{“number”:”13700000000”,”params”:\[“小王”,”小李”,”小周”\]\}\]|TTS模板的变量值，格式为JSON。必须和具体的号码对应、TtsParam和上面的TtsParamHead变量名称一一对应。

 |
|TtsParamHead|String|否|\[“name1”,”name2”,”name3”\]|带变量的呼叫任务，格式为JSON。变量名称列表，和下面的ttsParam配合使用。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|请求状态码。

 -   返回OK代表请求成功。
-   其他错误码详见[错误码列表](~~112502~~)。

 |
|Data|String|1045001|机器人呼叫任务的唯一任务ID，可通过此ID调用QueryRobotTaskDetail API查询任务详情。

 |
|Message|String|OK|状态码的描述。

 |
|RequestId|String|D9CB3933-9FE3-4870-BA8E-2BEE91B69D23|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=UploadRobotTaskCalledFile
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<UploadRobotTaskCalledFileResponse>
  <Message>OK</Message>
  <RequestId>D9CB3933-9FE3-4870-BA8E-2BEE91B69D23</RequestId>
  <Code>OK</Code>
  <Data>4001112222</Data>
</UploadRobotTaskCalledFileResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Data":"1045001",
	"Message":"OK",
	"RequestId":"D9CB3933-9FE3-4870-BA8E-2BEE91B69D23",
	"Code":"OK"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Dyvmsapi)查看更多错误码。

