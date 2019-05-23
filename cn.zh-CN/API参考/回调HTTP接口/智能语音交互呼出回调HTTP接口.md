# 智能语音交互呼出回调HTTP接口 {#concept_ejb_3sp_fhb .concept}

语音平台通过APISmartCall发起呼叫后，可以通过智能外呼回调HTTP接口，在通话中把转换后的语音文本回传给业务方，业务方把下一步的执行动作返回给语音平台，以此完成机器人与用户通话中的智能语音交互。

平台通过HTTP协议实时推送语音转写的文本时，即使用户静音也会发送异常状态。在消息的响应中可以设置播放语音、终止播放当前语音、转接人工坐席、挂机等动作指示平台接下来的执行动作。

**说明：** 智能外呼回调HTTP接口必须和API接口SmartCall配合使用，通过SmartCall发起呼叫任务，并使用回调接口回传语音文本，并接收业务方指定的下一步动作。

## 业务流程 {#section_ttm_evf_hqv .section}

使用智能语音交互呼出回调HTTP接口，请参考以下业务流程：

1.  平台设置。
    1.  在**通用管理** \> **服务开通**页面开启**智能语音交互通话呼出**。
    2.  [启用回调接口](#section_r5x_t3h_hhb)，设置回调地址。
2.  通过SmartCall接口发起呼叫任务。
3.  自动调用智能语音交互呼入回调HTTP接口，接收接收通话过程中用户语音实时转写的文本消息。
4.  业务方把下一步的执行动作返回给语音平台。

## 启用回调接口 {#section_r5x_t3h_hhb .section}

使用智能外呼回调HTTP接口之前，需要先在控制台上开启订阅。

1.  登录[语音服务控制台](https://dyvms.console.aliyun.com/dyvms.htm#/account)。
2.  在左侧导航栏中单击通用管理。
3.  在订阅回执消息页签中找到**智能外呼ASR实时交互**。
4.  单击开启功能开关。
5.  根据页面提示设置响应信息。
6.  填写接收地址。

    此处填写的接收地址是固定接收地址，用于接收语音实时转文本结果并返回下一步执行动作。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/150139/155861219242288_zh-CN.png)

7.  单击**保存**。

## 回调接口规范 {#section_mrt_pgh_hhb .section}

|规范|说明|
|:-|:-|
|接口协议|HTTP|
|方式|POST|
|字符编码格式|UTF-8|

## 请求样例 {#section_pxz_vgh_hhb .section}

```
http://127.0.0.1/test?call_id=100001616500^100001871490&timestamp=1504174341229&content_type=normal&content={"role“: “B”,”identity”: “id2”,”words”: “你好”,”begin_offset”: “1000”,”end_offset”: “9000”,”begin_time”: “2017-06-01 10:00:00”}
```

## 请求参数 {#section_p1m_qgh_hhb .section}

|参数名称|参数类型|是否必填|示例|说明|
|----|----|----|--|--|
|call\_id|String|必须|123^321|这通呼叫的唯一ID。|
|timestamp|Long|必须|1504174341229|当前时间戳。|
|content\_type|String|必须|normal|消息类型，包括： -   **normal**：标准
-   **mute**：静音
-   **timebreak**：按时长打断消息
-   **dtmf**：按键消息
-   **parallel\_transfer**：并行转接状态

 |
|content|JSON|必须|\{“role”: “B”,”identity”: “id2”,”words”: “你好”,”begin\_offset”: “1000”,”end\_offset”: “9000”,”begin\_time”: “2017-06-01 10:00:00”\}|具体的语音内容，JSON格式。详细说明请参考下表。|

-   ****content\_type为normal时，Content参数说明：**** 

    |名称|格式|是否必填|示例|说明|
    |--|--|----|--|--|
    |role|String|必须|B|对话内容角色|
    |identity|Long|必须|id2|对话角色的具体身份标识|
    |words|String|必须|你好|这个角色说的一句话|
    |begin\_offset|String|必须|6000000|相对本次会话起始点的开始时间偏移时间，单位为毫秒|
    |end\_offset|String|必须|7000000|相对本次会话起始点的结束时间偏移，单位为毫秒|
    |begin\_time|String|必须|7000000|通话开始时间，单位为秒|
    |is\_playing|String|可选|true|是否正在播放语音|
    |current\_media\_code|String|可选|xxxx.wav|当前播放的语音文件，当值为early\_media 时，表示为早媒体消息。|
    |dynamic\_id|String|可选|abcdefgh|预留给调用方使用的动态扩展id，在下次回调地址中带回，用于客户的开发标识需要|
    |record\_begin\_time|Long|可选|1543856399000|录音开始时间|
    |asr\_begin\_time|String|可选|1543856399000|用户开始说话时间。Unix时间戳格式，单位为毫秒|
    |asr\_end\_time|String|可选|1543856399000|用户结束说话时间。Unix时间戳格式，单位为毫秒|
    |play\_begin\_time|String|可选|1543856399000|服务器开始放音时间。Unix时间戳格式，单位为毫秒|
    |play\_end\_time|String|可选|1543856399000|服务器放音结束时间。Unix时间戳格式，单位为毫秒。如果播放未结束，则为0|

-   **content\_type为mute时，Content参数说明：** 

    |名称|格式|是否必填|示例|说明|
    |--|--|----|--|--|
    |dynamic\_id|String|可选|abcdefgh|预留给调用方使用的动态扩展id，在下次回调地址中带回，用于客户的开发标识需要|

-   **content\_type为dtmf时，Content参数说明：** 

    |名称|格式|是否必填|示例|说明|
    |--|--|----|--|--|
    |dynamic\_id|String|可选|abcdefgh|预留给调用方使用的动态扩展id，在下次回调地址中带回，用于客户的开发标识需要|
    |dtmf\_digits|String|可选|1|context\_type为dtmf时的特有字段，代表用户的按键返回，如果用户超时未返回按键，则返回noInputTimeout字符串|

-   **content\_type为timebreak时，Content参数说明：** 

    |名称|格式|是否必填|示例|说明|
    |--|--|----|--|--|
    |current\_media\_code|String|可选|xxxx.wav|当前播放的语音文件|
    |asr\_begin\_time|String|可选|1543856399000|用户开始说话时间。Unix时间戳格式，单位为毫秒|
    |play\_begin\_time|String|可选|1543856399000|服务器开始放音时间。Unix时间戳格式，单位为毫秒|
    |dynamic\_id|String|可选|abcdefgh|预留给调用方使用的动态扩展id，在下次回调地址中带回，用于客户的开发标识需要|

-   **content\_type为parallel\_transfer时，Content参数说明：** 

    |名称|格式|是否必填|示例|说明|
    |--|--|----|--|--|
    |dynamic\_id|String|可选|abcdefgh|预留给调用方使用的动态扩展id，在下次回调地址中带回，用于客户的开发标识需要|
    |transfer\_status|String|可选|success\\fail|并行转接状态，是否成功|
    |fail\_cause|String|可选|transfer fail.|转接失败原因|
    |is\_monitor|Boolean|可选|true|呼叫中心并行转接成功后是否监控|
    |cc\_name|String|可选|aliyun\_cc|并行转接成功后呼叫中心名称|


## 返回示例 {#section_icj_ghh_hhb .section}

以JSON格式为例，返回示例如下：

-   调用成功：

    ```
    {“result”: “success”,”msg”: “成功”,“data”: {“call_id”: “100001616500^100001871490”,”action”: “play”,”action_code”: “411111”,”extend”: “xxxx”}}
    ```

-   调用失败：

    ```
    {“result”:”fail”,”msg”:”fail reason”, “data”:{}}
    ```


## 返回参数 {#section_kw1_hhh_hhb .section}

|名称|格式|是否必填|示例|说明|
|--|--|----|--|--|
|call\_id|String|必须|B|这通呼叫的唯一ID|
|action|String|必须|play|下一步的动作： -   **play**：播放下一段语音
-   **break**：打断当前正在播放的语音
-   **continue**：继续播放当前语音
-   **hangup**：挂机
-   **transfer**：转接
-   **donothing**：不做任何处理
-   **dtmf**：接收dtmf消息
-   **parallel\_transfer**：并行转接命令
-   **parallel\_bridge**：并行桥接命令

**说明：** 当请求参数is\_monitor为true时，请勿使用parallel\_bridge命令。


 |
|action\_break|Boolean|可选|true|当前动作是否可以打断，默认是true，可打断|
|action\_code|String|必须|abc.wav,def.wav,$name$|播放的语音文件code，支持多文件播放，多个文件使用英文逗号（,）分隔，支持tts参数，使用$|
|action\_code\_break|Boolean|可选|true|返回的媒体文件是否可以打断，默认是true，可打断；action\_break和action\_code\_break，action\_code\_break优先级更高|
|mute\_time|Integer|可选|10000|静音时长，单位为毫秒。取值范围为1000~20000，超过这个范围默认10000|
|dynamic\_id|String|可选|abc|预留给调用方使用的动态扩展id，在下次回调地址中带回，用于客户的开发标识需要|
|action\_code\_param|String|可选|\{“name”:”喂，你好”\}|tts参数，json格式，key和action\_code对应|
|number|String|可选|13711111111|转接手机号码，action设为transfer时有效|
|action\_code\_time\_break|Integer|可选|120|基于用户持续说话时长打断，单位为毫秒。在ationCodeBreak为true时并且取值大于0时生效|
|dtmf\_nonin\_overtime|Integer|可选|3|dtmf命令时的特有字段，表示无输入超时时间，默认值3s。取值范围为3s~60s。|
|dtmf\_max\_numbers|Integer|可选|5|dtmf命令时的特有字段，表示最大收号长度，取值范围为1~50。|
|dtmf\_end\_character|String|可选|\#|dtmf命令时的特有字段，表示收号停止符号，只支持 \* \#，支持空|
|transfer\_playfile|String|可选|\#|并行转接成功后给坐席播放音频文件|
|is\_monitor|Boolean|可选|true|呼叫中心并行转接成功后是否监控|
|cc\_name|String|可选|aliyun\_cc|并行转接成功后呼叫中心名称|

