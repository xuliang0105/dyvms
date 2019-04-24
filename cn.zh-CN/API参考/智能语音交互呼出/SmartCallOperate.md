# SmartCallOperate {#doc_api_Dyvmsapi_SmartCallOperate .reference}

调用接口SmartCallOperate在智能外呼通话中，发起指定动作。

在智能语音交互呼出通话中，转接呼叫中心坐席时，可以使用接口**SmartCallOperate**指定被叫号码发起指定动作。

**说明：** 当前仅支持指定动作为被叫号码与呼叫中心坐席桥接。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Dyvmsapi&api=SmartCallOperate)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CallId|String|是|116012854210^102814279210|通话的唯一回执ID，由接口**SmartCall**返回。

 |
|Command|String|是|parallelBridge|在智能外呼通话中，指定被叫号码发起的动作。

 **说明：** 当前仅支持参数**parallelBridge**，表示指定动作为被叫号码与呼叫中心坐席桥接。

 |
|AccessKeyId|String|否|LTAIP00vvvvvvvvv|主账号AccessKey的ID。

 |
|Action|String|否|SmartCallOperate|系统规定参数。取值：**SmartCallOperate**。

 |
|Param|String|否|Param|扩展字段。

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
|RequestId|String|A90E4451-FED7-49D2-87C8-00700A8C4D0D|请求ID。

 |
|Status|Boolean|true|命令执行的结果，其中：

 -   **true**：命令执行成功。
-   **false**：命令执行失败。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=SmartCallOperate
&CallId=116012854210^102814279210
&Command=parallelBridge
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<SmartCallOperateResponse>
  <Code>OK</Code>
  <Message>OK</Message>
  <RequestId>A90E4451-FED7-49D2-87C8-00700A8C4D0D</RequestId>
  <Status>true</Status>
</SmartCallOperateResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Status":"true",
	"Message":"OK",
	"RequestId":"A90E4451-FED7-49D2-87C8-00700A8C4D0D",
	"Code":"OK"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Dyvmsapi)

