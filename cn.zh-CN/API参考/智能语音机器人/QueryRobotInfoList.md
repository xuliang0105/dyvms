# QueryRobotInfoList {#doc_api_Dyvmsapi_QueryRobotInfoList .reference}

调用接口QueryRobotInfoList查看机器人列表。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Dyvmsapi&api=QueryRobotInfoList&type=RPC&version=2017-05-25)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|AccessKeyId|String|否|LTAIP00vvvvvvvvv|主账号AccessKey的ID。

 |
|Action|String|否|QueryRobotInfoList|系统规定参数。取值：**SendBatchSms**。

 |
|AuditStatus|String|否|AUDITING|审核状态，包括：

 -   **CONFIGURABLE**：可配置。
-   **AUDITING**：审核中 。
-   **AUDITPASS**：审核通过。
-   **AUDITFAIL**：审核失败。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|OK|请求状态码。

 -   返回OK代表请求成功。
-   其他错误码详见[错误码列表](~~112502~~)。

 |
|Data|String|\{\\"id\\":1000010920004,\\"gmtModified\\":\\"Thu Mar 21 15:38:55 CST 2019\\",\\"auditStatus\\":\\"AUDITPASS\\",\\"gmtCreate\\":\\"Thu Mar 21 12:00:51 CST 2019\\",\\"remark\\":\\"测试勿删，测试请通过\\",\\"partnerId\\":100000022670001,\\"asrId\\":\\"a9a1d69081fd4266ad788346bf5e1b6c\\",\\"robotType\\":\\"CUSTOM\\",\\"asrType\\":\\"1\\",\\"robotName\\":\\"催收场景5--ssml标记2-RVR-副本\\"\},\{\\"id\\":1000010920003,\\"gmtModified\\":\\"Thu Mar 21 11:51:10 CST 2019\\",\\"auditStatus\\":\\"AUDITPASS\\",\\"gmtCreate\\":\\"Thu Mar 21 11:44:57 CST 2019\\",\\"remark\\":\\"测试勿删，内部测试请通过\\",\\"partnerId\\":100000022670001,\\"asrId\\":\\"a9a1d69081fd4266ad788346bf5e1b6c\\",\\"robotType\\":\\"CUSTOM\\",\\"asrType\\":\\"1\\",\\"robotName\\":\\"催收场景5-ssml标记2-RVR\\"\}|机器人的基本信息，JSON格式。参数如下：

 -   **id**：机器人id。
-   **robotName**：机器人名称。
-   **robotType**：机器人类型。分为哪几种》
-   **auditStatus**：审核状态。
-   **gmtCreate**：创建时间。
-   **gmtModified**：修改时间。
-   **partnerId**：合作伙伴ID。
-   **asrId**：ASR模型ID。
-   **asrType**：ASR类型，包括**公有**和**私有**。

 |
|Message|String|OK|状态码的描述。

 |
|RequestId|String|F59AF338-655D-48E8-9471-5EB07692B1CC|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=QueryRobotInfoList
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<QueryRobotInfoListResponse>
	  <Data>[{"id":1000010920004,"gmtModified":"Thu Mar 21 15:38:55 CST 2019","auditStatus":"AUDITPASS","gmtCreate":"Thu Mar 21 12:00:51 CST 2019","remark":"测试勿删，测试请通过","partnerId":100000022670001,"asrId":"a9a1d69081fd4266ad788346bf5e1b6c","robotType":"CUSTOM","asrType":"1","robotName":"催收场景5-ssml标记2-RVR-副本"},{"id":1000010920003,"gmtModified":"Thu Mar 21 11:51:10 CST 2019","auditStatus":"AUDITPASS","gmtCreate":"Thu Mar 21 11:44:57 CST 2019","remark":"测试勿删，测试请通过","partnerId":100000022670001,"asrId":"a9a1d69081fd4266ad788346bf5e1b6c","robotType":"CUSTOM","asrType":"1","robotName":"催收场景-ssml标记2-RVR"}}]</Data>
	  <Message>OK</Message>
	  <RequestId>E8EF9B41-C4DC-44D5-A25B-DA9AC7791998</RequestId>
	  <Code>OK</Code>
</QueryRobotInfoListResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Data":"[{\"id\":1000010920004,\"gmtModified\":\"Thu Mar 21 15:38:55 CST 2019\",\"auditStatus\":\"AUDITPASS\",\"gmtCreate\":\"Thu Mar 21 12:00:51 CST 2019\",\"remark\":\"测试勿删，测试请通过\",\"partnerId\":100000022670001,\"asrId\":\"a9a1d69081fd4266ad788346bf5e1b6c\",\"robotType\":\"CUSTOM\",\"asrType\":\"1\",\"robotName\":\"催收场景5--ssml标记2-RVR-副本\"},{\"id\":1000010920003,\"gmtModified\":\"Thu Mar 21 11:51:10 CST 2019\",\"auditStatus\":\"AUDITPASS\",\"gmtCreate\":\"Thu Mar 21 11:44:57 CST 2019\",\"remark\":\"测试勿删，内部测试请通过\",\"partnerId\":100000022670001,\"asrId\":\"a9a1d69081fd4266ad788346bf5e1b6c\",\"robotType\":\"CUSTOM\",\"asrType\":\"1\",\"robotName\":\"催收场景5-ssml标记2-RVR\"}]",
	"Message":"OK",
	"RequestId":"E8EF9B41-C4DC-44D5-A25B-DA9AC7791998",
	"Code":"OK"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Dyvmsapi)查看更多错误码。

