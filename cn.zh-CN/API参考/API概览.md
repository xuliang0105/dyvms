# API概览 {#concept_spb_fdn_hhb .concept}

本文档为您展示语音服务所有可调用的API接口，详细接口信息请参考对应接口文档。

更多 API 资源，请访问 [OpenAPI Explorer](https://api.aliyun.com/)。

## 语音通知接口 {#section_ix1_xcs_ggb .section}

|API|描述|
|:--|:-|
|[SingleCallByVoice](cn.zh-CN/API参考/语音通知/SingleCallByVoice.md)|调用接口SingleCallByVoice发起语音文件类型的语音通知。|
|[SingleCallByTts](cn.zh-CN/API参考/语音通知/SingleCallByTts.md)|调用接口SingleCallByTts发起语音通知，播放的音频为文本转语音模板转换后的音频文件。|
|[IvrCall](cn.zh-CN/API参考/语音通知/IvrCall.md)|调用接口IvrCall发起交互式语音通话。|

## 点击呼叫接口 {#section_ktk_xcs_ggb .section}

|API|描述|
|:--|:-|
|[ClickToDial](cn.zh-CN/API参考/点击呼叫/ClickToDial.md)|调用接口ClickToDial发起一次双方通话。|
|[CancelCall](cn.zh-CN/API参考/点击呼叫/CancelCall.md)|调用接口CancelCall取消点击呼叫接口ClickToDial发起的呼叫。|

## 智能语音交互呼出接口 {#section_z1s_xcs_ggb .section}

|API|描述|
|:--|:-|
|[SmartCall](cn.zh-CN/API参考/智能语音交互呼出/SmartCall.md)|调用接口SmartCall发起智能语音交互通话。|

## 回调HTTP接口 {#section_fyb_qwh_hhb .section}

|API|描述|
|:--|:-|
|[智能外呼回调HTTP接口](cn.zh-CN/API参考/回调HTTP接口/智能外呼回调HTTP接口.md)|语音平台通过API **SmartCall**发起呼叫后，可以通过智能外呼回调HTTP接口，在通话中把转换后的语音文本回传给业务方，业务方把下一步的执行动作返回给语音平台，以此完成机器人与用户通话中的智能语音交互。|
|[动态IVR呼转回调接口](cn.zh-CN/API参考/回调HTTP接口/动态IVR呼转回调接口.md)|语音服务支持在控制台上对全局添加号码回拨设置，当客户回拨号码时，在通话中播放指定录音文件或设置动态IVR。|

## 智能语音机器人接口 {#section_asq_mwh_hhb .section}

|API|描述|
|:--|:-|
|[BatchRobotSmartCall](cn.zh-CN/API参考/智能语音机器人/BatchRobotSmartCall.md)|调用接口BatchRobotSmartCall发起机器人外呼任务。|
|[QueryRobotInfoList](cn.zh-CN/API参考/智能语音机器人/QueryRobotInfoList.md)|调用接口QueryRobotInfoList查看机器人列表。|
|[QueryCallDetailByTaskId](cn.zh-CN/API参考/智能语音机器人/QueryCallDetailByTaskId.md)|调用接口QueryCallDetailByTaskId查看指定机器人外呼任务的话单详情。|

## 呼叫记录查询接口 {#section_wjq_nwh_hhb .section}

|API|描述|
|:--|:-|
|[QueryCallDetailByCallId](cn.zh-CN/API参考/呼叫记录查询/QueryCallDetailByCallId.md)|调用接口QueryCallDetailByCallId查询指定通话的呼叫详情。|

## 回执消息 {#section_qhp_pwh_hhb .section}

|API|描述|
|:--|:-|
|[呼叫记录消息（VoiceReport）](cn.zh-CN/API参考/消息回执/VoiceReport.md)|订阅呼叫记录消息（VoiceReport）可以在呼叫结束后获取呼叫的记录信息，包括通话时长、结束原因等。|
|[录音记录消息（VoiceCallReport）](cn.zh-CN/API参考/消息回执/VoiceReport.md)|订阅呼叫中间状态消息（VoiceCallReport），可以获取呼叫的的中间状态信息，例如状态产生的时间等。|
|[呼叫记录消息（VoiceRecordReport）](cn.zh-CN/API参考/消息回执/VoiceReport.md)|订阅录音记录消息（VoiceRecordReport），可以在通话结束后获取通话的录音记录。|
|[ASR实时消息（VoiceRTASRReport）](cn.zh-CN/API参考/消息回执/VoiceReport.md)|订阅ASR实时消息（VoiceRTASRReport），可以获取通话的实时文本转换结果。|

