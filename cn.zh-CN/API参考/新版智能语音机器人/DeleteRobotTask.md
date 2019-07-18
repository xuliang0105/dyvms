# DeleteRobotTask {#doc_api_Dyvmsapi_DeleteRobotTask .reference}

删除智能语音任务。

删除智能语音任务。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Dyvmsapi&api=DeleteRobotTask)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|AccessKeyId|String|否|LTAIP00vvvvvvvvv|主账号AccessKey的ID。

 |
|Action|String|否|DeleteRobotTask|系统规定参数。取值：**DeleteRobotTask**。

 |
|TaskId|Long|否|1045001|机器人呼叫任务的唯一任务ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|请求状态码。

 -   返回OK代表请求成功。
-   其他错误码详见[错误码列表](~~112502~~)。

 |
|Data|String|true|是否成功

 |
|Message|String|OK|状态码的描述。

 |
|RequestId|String|D9CB3933-9FE3-4870-BA8E-2BEE91B69D23|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DeleteRobotTask
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DeleteRobotTaskResponse>
  <Message>OK</Message>
  <RequestId>D9CB3933-9FE3-4870-BA8E-2BEE91B69D23</RequestId>
  <Code>OK</Code>
  <TaskId>4001112222</TaskId>
</DeleteRobotTaskResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Data":true,
	"Message":"OK",
	"RequestId":"D9CB3933-9FE3-4870-BA8E-2BEE91B69D23",
	"Code":"OK"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Dyvmsapi)查看更多错误码。

