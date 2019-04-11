# QueryCallDetailByTaskId {#doc_api_Dyvmsapi_QueryCallDetailByTaskId .reference}

调用接口QueryCallDetailByTaskId查看指定机器人外呼任务的话单详情。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Dyvmsapi&api=QueryCallDetailByTaskId)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Callee|String|是|15900000000| 被叫号码。当前仅支持查看一个被叫号码的外呼记录。

 |
|QueryDate|Long|是|123456789000| 机器人外呼任务的开始时间。Unix时间戳格式。

 **说明：** 单位为毫秒。

 |
|TaskId|String|是|4001112222| 机器人呼叫任务的唯一任务ID，成功下发机器人外呼任务后返回。可以在控制台 [任务列表](https://dyvms.console.aliyun.com/dyvms.htm#/smart-call/saas/task/list) 中查看，或调用接口 **BatchRobotSmartCall** 成功后记录返回的参数 **TaskId** 。

 |
|AccessKeyId|String|否|LTAIP00vvvvvvvvv| 主账号AccessKey的ID。

 |
|Action|String|否|QueryCallDetailByTaskId| 系统规定参数。取值： **QueryCallDetailByTaskId** 。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK| 请求状态码。

 -   返回OK代表请求成功。
-   其他错误码详见 [错误码列表](~~112502~~) 。

 |
|Data|String|\{"rejectCount":0,"dialogCount":3,"tags":"","startDate":"2019-03-27 10:34:54","gmtCreate":"2019-03-27 10:34:40","sureCount":0,"state":"200000","recordFile":"http://alicom-fc-record-biz.cn-hangzhou.oss.aliyun-inc.com/Freeswitch\_RU\_115987800002\_02c3554f-ea24-422d-b1de-e671f455f21a\_record.wav?OSSAccessKeyId=bypFNbGJVk73PsLI&amp;Signature=VWHOX%2FFhvvtSkxfMTw%2F5fdJUQuk%3D&amp;Expires=1554382725","defaultCount":0,"endDate":"2019-03-27 10:35:09","calleeShowNumber":"053158552960","customCount":0,"callId":"115987800002^102789420002","knowledgeCount":0,"recordStatus":1,"denyCount":0,"duration":16,"stateDesc":"鐢ㄦ埛鎺ュ惉","knowledgeCommonCount":0,"callee":"13735460951","knowledgeBusinessCount":0,"hangupDirection":1\}| 机器人外呼任务的话单详情，JSON格式。参数包括：

 -   **startDate** ：应答时间。
-   **stateDesc** ：挂机原因，有早媒体状态码的情况下，使用早媒体码的原因。
-   **statusCode** ：状态码。
-   **endDate** ：结束时间。
-   **calleeShowNumber** ：主叫号显。
-   **callee** ：被叫号码。
-   **duration** ：计费时长。
-   **gmtCreate** ：创建时间。
-   **hangupDirection** ：挂机方向。
-   **tags** ：标签。
-   **dialogCount** ：对话轮次。
-   **sureCount** ：肯定次数。
-   **denyCount** ：否定次数。
-   **rejectCount** ：拒绝次数。
-   **customCount** ：自定义次数。
-   **knowledgeCount** ：知识库次数。
-   **recordFile** ：录音文件下载地址，URL的过期时间为48小时，请及时下载。
-   **callId** ：通话ID。
-   **recordStatus** ：录音文件状态。其中：
    -   1：有录音文件。
    -   2：没有录音文件。
-   **knowledgeCommonCount** ：知识库通用问题字数。
-   **knowledgeBusinessCount** ：知识库业务问题字数。
-   **callee** ：被叫号码。
-   **dialogDetail** ：对话明细，一个JSON数组。其中包括：
    -   **role** ：发言对象。
    -   **content** ：发言内容。
    -   **time** ：发言时间。

 |
|Message|String|OK| 状态码的描述。

 |
|RequestId|String|D86B61A8-F2EE-4E4C-9F05-08A4676FFD89| 请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Callee=15900000000
&QueryDate=123456789000
&TaskId=4001112222
&<公共请求参数>
			
```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<QueryCallDetailByTaskIdResponse>
  <Data><![CDATA[{"rejectCount":0,"dialogCount":3,"tags":"","startDate":"2019-03-27 10:34:54","gmtCreate":"2019-03-27 10:34:40","sureCount":0,"state":"200000","recordFile":"http://alicom-fc-record-biz.cn-hangzhou.oss.aliyun-inc.com/Freeswitch_RU_115987800002_02c3554f-ea24-422d-b1de-e671f455f21a_record.wav?OSSAccessKeyId=bypFNbGJVk73****&Signature=VWHOX%2FFhvvtSkxfMTw%2F5fdJUQu****&Expires=1554382725","defaultCount":0,"endDate":"2019-03-27 10:35:09","calleeShowNumber":"053158552960","customCount":0,"callId":"115987800002^102789420002","dialogDetail":[{"content":"我的呼叫测试","startTime":"Wed Mar 27 10:34:45 CST 2019","role":"robot"},{"content":"喂，哎，你好","startTime":"Wed Mar 27 10:35:00 CST 2019","role":"custom"},{"content":"不好意思，可以慢点再说一遍吗?","startTime":"Wed Mar 27 10:35:00 CST 2019","role":"robot"},{"content":"喂","startTime":"Wed Mar 27 10:35:01 CST 2019","role":"custom"},{"content":"哦再见","startTime":"Wed Mar 27 10:35:08 CST 2019","role":"custom"},{"content":"不好意思，我这边听得不是很清楚，您可以再说一遍吗？","startTime":"Wed Mar 27 10:35:08 CST 2019","role":"robot"}],"knowledgeCount":0,"recordStatus":1,"denyCount":0,"duration":16,"stateDesc":"鐢ㄦ埛鎺ュ惉","knowledgeCommonCount":0,"callee":"13735460951","knowledgeBusinessCount":0,"hangupDirection":1}]]</Data>
  <Message>OK</Message>
  <RequestId>068FCADA-78C6-4A14-A586-2E01CF91E036</RequestId>
  <Code>OK</Code>
</QueryCallDetailByTaskIdResponse>
			
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Data":"{\"rejectCount\":0,\"dialogCount\":3,\"tags\":1,\"startDate\":\"2019-03-27 10:34:54\",\"gmtCreate\":\"2019-03-27 10:34:40\",\"sureCount\":0,\"state\":\"200000\",\"recordFile\":\"http://alicom-fc-record-biz.cn-hangzhou.oss.aliyun-inc.com/Freeswitch_RU_115987800002_02c3554f-ea24-422d-b1de-e671f455f21a_record.wav?OSSAccessKeyId=bypFNbGJVk73****&Signature=VWHOX%2FFhvvtSkxfMTw%2F5fdJUQu****&Expires=1554382725\",\"defaultCount\":0,\"endDate\":\"2019-03-27 10:35:09\",\"calleeShowNumber\":\"053158552960\",\"customCount\":0,\"callId\":\"115987800002^102789420002\",\"dialogDetail\":[{\"content\":\"我的呼叫测试\",\"startTime\":\"Wed Mar 27 10:34:45 CST 2019\",\"role\":\"robot\"},{\"content\":\"喂，哎，你好\",\"startTime\":\"Wed Mar 27 10:35:00 CST 2019\",\"role\":\"custom\"},{\"content\":\"不好意思，可以慢点再说一遍吗?\",\"startTime\":\"Wed Mar 27 10:35:00 CST 2019\",\"role\":\"robot\"},{\"content\":\"喂\",\"startTime\":\"Wed Mar 27 10:35:01 CST 2019\",\"role\":\"custom\"},{\"content\":\"哦再见\",\"startTime\":\"Wed Mar 27 10:35:08 CST 2019\",\"role\":\"custom\"},{\"content\":\"不好意思，我这边听得不是很清楚，您可以再说一遍吗？\",\"startTime\":\"Wed Mar 27 10:35:08 CST 2019\",\"role\":\"robot\"}],\"knowledgeCount\":0,\"recordStatus\":1,\"denyCount\":0,\"duration\":16,\"stateDesc\":\"鐢ㄦ埛鎺ュ惉\",\"knowledgeCommonCount\":0,\"callee\":\"13735460951\",\"knowledgeBusinessCount\":0,\"hangupDirection\":1}",
	"Message":"OK",
	"RequestId":"D86B61A8-F2EE-4E4C-9F05-08A4676FFD89",
	"Code":"OK"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Dyvmsapi)

