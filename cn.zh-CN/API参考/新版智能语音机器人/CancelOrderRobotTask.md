# CancelOrderRobotTask {#doc_api_Dyvmsapi_CancelOrderRobotTask .reference}

调用CancelOrderRobotTask取消定时启动智能语音任务。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Dyvmsapi&api=CancelOrderRobotTask&type=RPC&version=2017-05-25)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|AccessKeyId|String|否|LTAIP00vvvvvvvvv|主账号AccessKey的ID。

 |
|Action|String|否|CancelOrderRobotTask|系统规定参数。取值：**CancelOrderRobotTask**。

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

http(s)://[Endpoint]/?Action=CancelOrderRobotTask
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CancelOrderRobotTaskResponse>
	  <Message>OK</Message>
	  <RequestId>D9CB3933-9FE3-4870-BA8E-2BEE91B69D23</RequestId>
	  <Code>OK</Code>
	  <Data>true</Data>
</CancelOrderRobotTaskResponse>
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

