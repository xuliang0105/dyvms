# CancelCall {#doc_api_Dyvmsapi_CancelCall .reference}

调用接口CancelCall取消点击呼叫接口ClickToDial发起的呼叫。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Dyvmsapi&api=CancelCall&type=RPC&version=2017-05-25)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CallId|String|是|116012854210^102814279210|此次通话的唯一回执ID，可以从接口**ClickToDial**的返回信息中获取。

 |
|AccessKeyId|String|否|LTAIP00vvvvvvvvv|主账号AccessKey的ID。

 |
|Action|String|否|CancelCall|系统规定参数。取值：**CancelCall**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|请求状态码。

 -   返回OK代表请求成功。
-   其他错误码详见[错误码列表](~~112502~~)。

 |
|Message|String|OK|状态码的描述。

 |
|RequestId|String|F655A8D5-B967-440B-8683-DAD6FF8DE990|请求ID。

 |
|Status|Boolean|true|是否成功取消呼叫。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?CallId=116012854210^102814279210
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CancelCallResponse>
	  <Code>OK</Code>
	  <Message>OK</Message>
	  <RequestId>D9CB3933-9FE3-4870-BA8E-2BEE91B69D23</RequestId>
	  <Status>true</Status>
</CancelCallResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Status":"true",
	"Message":"OK",
	"RequestId":"D9CB3933-9FE3-4870-BA8E-2BEE91B69D23",
	"Code":"OK"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Dyvmsapi)查看更多错误码。

