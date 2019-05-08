# 智能语音交互呼入回调HTTP接口 {#concept_261502 .concept}

用户拨打配置智能语音交互呼入的号码发起呼叫后，通过智能语音交互呼入回调HTTP接口，接收通话过程中用户语音实时转写的文本消息，业务方把下一步的执行动作返回给语音平台，以此完成机器人与用户通话中的智能语音交互。

平台通过HTTP协议实时推送语音转写的文本时，即使用户无回复也会发送相应异常状态。在消息的响应中可以设置播放语音、终止播放当前语音、转接人工坐席、挂机等动作指示平台接下来的执行动作。

## 业务流程 {#section_nk6_yta_w3s .section}

使用智能语音交互呼入回调HTTP接口，请参考以下业务流程：

1.  平台设置。
    1.  在**通用管理** \> **服务开通**页面开启**智能语音交互通话呼入**。
    2.  在**通用管理** \> **呼入设置**页面为提供呼入服务的号码[添加呼入配置](#section_eek_aq0_7fi)。
    3.  [启用回调接口](#section_r5x_t3h_hhb)，设置回调地址。
2.  用户对指定号码发起呼叫。
3.  自动调用智能语音交互呼入回调HTTP接口，接收接收通话过程中用户语音实时转写的文本消息。
4.  业务方把下一步的执行动作返回给语音平台。

## 为指定号码添加呼入配置 {#section_eek_aq0_7fi .section}

购买号码后，如果确定通过该号码对望提供智能语音交互呼入服务，必须为该号码添加呼入配置，并设置配置类型为智能语音交互呼入。

1.  登录[语音服务控制台](https://dyvms.console.aliyun.com/dyvms.htm#/account)。
2.  在左侧导航栏中单击通用管理。
3.  在呼入设置页签中单击**添加指定号码呼入配置**。
4.  **配置类型**设置为**智能语音交互呼入**。
5.  根据实际情况选择**资质类型**、**使用公司**、**被叫号码**和**配置说明**。
6.  单击**确定添加**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/215996/155731340146651_zh-CN.png)


## 启用回调接口 {#section_r5x_t3h_hhb .section}

使用智能外呼回调HTTP接口之前，需要先在控制台上开启订阅。

1.  登录[语音服务控制台](https://dyvms.console.aliyun.com/dyvms.htm#/account)。
2.  在左侧导航栏中单击通用管理。
3.  在订阅回执消息页签中找到**智能外呼ASR实时交互**。
4.  单击开启功能开关。
5.  根据页面提示设置响应信息。
6.  填写接收地址。

    此处填写的接收地址是固定接收地址，用于接收语音实时转文本结果并返回下一步执行动作。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/150139/155731340142288_zh-CN.png)

7.  单击**保存**。

## 回调接口规范 {#section_mrt_pgh_hhb .section}

|规范|说明|
|:-|:-|
|接口协议|HTTP|
|方式|POST|
|字符编码格式|UTF-8|

## 请求样例 {#section_pxz_vgh_hhb .section}

```
http://http://127.0.0.1/test?call_id=100001616500^100001871490&timestamp=1504174341229&content_type=callin&content={“caller”: “13711111111”,” callee”: “05711111111”,” orgcallee”: “057122222222” }/test?call_id=100001616500^100001871490&timestamp=1504174341229&content_type=normal&content={"role“: “B”,”identity”: “id2”,”words”: “你好”,”begin_offset”: “1000”,”end_offset”: “9000”,”begin_time”: “2017-06-01 10:00:00”}
```

## 请求参数 {#section_p1m_qgh_hhb .section}

|参数名称|参数类型|必填与否|示例|说明|
|----|----|----|--|--|
|call\_id|String|必须|123^321|呼叫的唯一ID。|
|content\_type|String|必须|callin|智能语音交互的类型，callin表示用户拨打指定号码发起呼叫。|
|content|JSON|必须|\{“caller”: “13711111111”,”callee”: “05711111111”,”orgcallee”: “057122222222”\}|具体的语音内容，JSON格式。 -   caller：呼入场景主叫号码。
-   callee：呼入场景被拨打的服务号码。
-   orgcallee：呼入场景下原始被叫号码。

 假设C为服务号码，用户B设置呼叫转移至号码C，用户A拨打号码B转接至C时，caller 为A、Callee为C、orgcallee为B。

 |

## 返回示例 {#section_icj_ghh_hhb .section}

以JSON格式为例，返回示例如下：

-   调用成功：

    ```
    {“result”: “success”,”msg”: “,”msg”: “成功”,“data”: {“call_id”: “100001616500^100001871490”,”action”: “answer”,”action_code”: “411111”,”session_timeout”: 180,”asr_model_id”: 1212312312,”asr_base_id”: “customer_service_8k”,”record_flag”: true,”mute_time”: 5000,”pause_time”: 100,”action_code_break”: true,”action_break”: true,”action_code_param”: “”,”action_code_time_break”: 120,”tts_conf”: true,”tts_style”: “xiaoyan”,”tts_volume”: 100,”tts_speed”: 0,”dynamic_id”: “xxxx”}}”,“data”: {“call_id”: “100001616500^100001871490”,”action”: “play”,”action_code”: “411111”,”extend”: “xxxx”}}
    ```

-   调用失败：

    ```
    {“result”:”fail”,”msg”:”fail reason”, “data”:{}}
    ```


## 返回参数 {#section_kw1_hhh_hhb .section}

|名称|格式|是否必填|示例|说明|
|--|--|----|--|--|
|call\_id|String|必须|B|这通呼叫的唯一ID|
|action|String|必须|play|下一步的动作： -   **answer**：开场白应答
-   **hangup**：挂机

 |
|session\_timeout|String|可选|120|最大通话时长，单位秒，超时后自动挂断|
|asr\_model\_id|String|可选|11323223q23e34|定制模型id，未指定时使用基础模型|
|asr\_base\_id|String|可选|11323223q23e34|基础模型|
|record\_flag|Boolean|可选|true|是否开启录音|
|mute\_time|Integer|可选|5000|静音时长，单位为毫秒|
|pause\_time|Integer|可选|500|断句时长，单位为毫秒|
|action\_code|String|可选|xxx.wav|放音文件|
|action\_code\_break|Boolean|可选|true|放音文件是否允许被打断|
|action\_break|Boolean|可选|true|是否打断当前的放音文件|
|action\_code\_param|Integer|可选|\{“name”:”喂，你好”\}|放音参数|
|action\_code\_time\_break|Integer|可选|120|基于用户持续说话时长打断，单位为毫秒。在ationCodeBreak为true时并且取值大于0时生效|
|dynamic\_id|String|可选|xxx|扩展字段|
|tts\_conf|Boolean|可选|true|TTS声音设置参数，为true时需要设置ttsStyle、ttsColume、ttsSpeed三个参数来设置声音风格 TTS变量播放时的声音风格|
|tts\_style|String|可选|xiaoyan|TTS变量播放时的声音风格|
|tts\_volume|String|可选|100|TTS变量播放时音量|
|tts\_speed|String|可选|0|TTS变量播放速度|

