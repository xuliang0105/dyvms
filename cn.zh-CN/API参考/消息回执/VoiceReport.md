# VoiceReport {#concept_ltm_wqj_fhb .concept}

订阅呼叫记录消息（VoiceReport）可以在呼叫结束后获取呼叫的记录信息，包括通话类型、通话的开始及结束时间、通话时长、结束原因等。

## 返回参数 {#section_avb_vkw_fhb .section}

|名称|类型|描述|示例|
|:-|:-|:-|:-|
|call\_id|String|呼叫ID|100001616500^100001871490|
|start\_time|String|通话开始时间，未接通则为空|2017-06-01 10:00:00|
|end\_time|String|通话结束时间，未接通则为空|2017-06-01 10:00:00|
|caller|String|主叫号码|057111111111|
|callee|String|被叫号码|13711111111|
|duration|String|通话时长，未接通为0|10|
|status\_code|String|呼叫结果状态码，状态码说明请查看[呼叫状态码](cn.zh-CN/API参考/消息回执/呼叫状态码.md)|200010|
|early\_media\_code|String|早媒体结果状态码，状态码说明请查看[呼叫状态码](cn.zh-CN/API参考/消息回执/呼叫状态码.md)|200010|
|hangup\_direction|String|挂断方向 -   用户
-   机器

 |用户|
|status\_msg|String|结果描述|执行完成|
|out\_id|String|扩展字段回传，将调用API时传入的字段返回，智能外呼SAAS助手相关API的out\_id内容为ALICOM\_SMART\_SAAS^111111^2222222，其中的111111为批次任务ID。|123456|
|dtmf|String|DTMF按键|123456|
|voice\_type|String|话单类型 -   voice为普通话单
-   asr为asr话单
-   smart\_transfer为智能外呼转接话单

 |voice|
|dialog\_id|String|话术ID，智能外呼SAAS助手专有|1000010970001|
|toll\_type|String|通话类型 -   LOCAL ：市话
-   PROVINCE：省内长途
-   DOMESTIC： 国内长途
-   INTERNATIONAL：国际长途

 |LOCAL|

