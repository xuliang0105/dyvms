# VoiceRTASRReport {#concept_b1g_zqj_fhb .concept}

订阅ASR实时消息（VoiceRTASRReport），可以获取通话的实时文本转换结果。

|名称|类型|描述|示例值|
|:-|:-|:-|:--|
|role|String|对话内容角色。|B|
|identity|String|对话角色的具体身份标识。|id2|
|words|String|这个角色说的一句话。|你好|
|begin\_offset|Integer|相对本次会话起始点的开始时间偏移时间。单位为毫秒。|1000|
|end\_offset|Integer|相对本次会话起始点的结束时间偏移。单位为毫秒。|9000|
|begin\_time|String|通话开始时间。|2017-06-01 10:00:00|
|call\_id|String|呼叫ID。|100001616500\\^100001871490|
|out\_id|String|扩展字段回传，将调用API时传入的字段返回。|xxxx|

