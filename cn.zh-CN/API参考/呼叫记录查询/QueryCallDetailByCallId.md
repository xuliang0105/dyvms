# QueryCallDetailByCallId {#doc_api_Dyvmsapi_QueryCallDetailByCallId .reference}

调用接口QueryCallDetailByCallId查询指定通话的呼叫详情。

-   当前支持查询智能语音机器人以外的呼叫详情。
-   请将接口**QueryCallDetailByCallId**的调用频率限制在100次/分钟之内。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Dyvmsapi&api=QueryCallDetailByCallId&type=RPC&version=2017-05-25)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CallId|String|是|116014888060^102816313060|通话的唯一识别ID。调用其他外呼接口发起通话后，返回参数中会携带**CallId**。

 |
|ProdId|Long|是|11000000300006|产品ID。

 -   **11000000300006**：语音通知。
-   **11010000138001**：语音验证码。
-   **11000000300005**：IVR。
-   **11000000300004**：点击拨号。
-   **11000000300009**：SIP。
-   **11030000180001**：智能外呼。

 |
|QueryDate|Long|是|1553774465|指定通话发生的时间，格式为Unix时间戳，单位毫秒。会查询这个时间点对应的一整天的记录。

 |
|AccessKeyId|String|否|LTAIP00vvvvvvvvv|主账号AccessKey的ID。

 |
|Action|String|否|QueryCallDetailByCallId|系统规定参数。取值：**QueryCallDetailByCallId**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|请求状态码。

 -   返回OK代表请求成功。
-   其他错误码详见[错误码列表](~~112502~~)。

 |
|Data|String|\{“caller”:”18767130000”,”startDate”:””,”stateDesc”:”502”,”duration”:0,”callerShowNumber”:”05344750000”,”gmtCreate”:”2017-11-27 20:09:06”,”state”:”502”,”endDate”:””,”calleeShowNumber”:”05344750000”,”callee”:”13735460000”\}|呼叫详情，其中：

 -   **caller**：主叫号码。
-   **startDate**：呼叫开始时间。
-   **stateDesc**：通话状态描述。
-   **duration**：通话时长。
-   **callerShowNumber**：主叫显号。
-   **gmtCreate**：通话请求的接收时间。
-   **state**：通话状态。
-   **endDate**：呼叫结束时间。
-   **calleeShowNumber**：被叫显号
-   **callee**：被叫号码。

 |
|Message|String|OK|状态码的描述。

 |
|RequestId|String|A90E4451-FED7-49D2-87C8-00700A8C4D0D|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=QueryCallDetailByCallId
&CallId=116014888060^102816313060
&ProdId=11000000300006
&QueryDate=1553774465
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<QueryCallDetailByCallIdResponse>
	  <Code>OK</Code>
	  <Data></Data>
	  <Message>OK</Message>
	  <RequestId>A90E4451-FED7-49D2-87C8-00700A8C4D0D</RequestId>
</QueryCallDetailByCallIdResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Data":"",
	"Message":"OK",
	"RequestId":"A90E4451-FED7-49D2-87C8-00700A8C4D0D",
	"Code":"OK"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Dyvmsapi)查看更多错误码。

