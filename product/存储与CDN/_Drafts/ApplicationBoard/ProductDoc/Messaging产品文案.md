## 简介

Messaging 是 MobileLine 的专业移动推送服务，支持百亿级的通知/消息推送，可以将相关信息及时送达精准定向的用户，并与用户持续友好互动，能大幅提升用户活跃度、留存率。



## 功能介绍

| 功能 | 简介 | 
| :---: | :---- |
|自定义推送通知| 提供自定义通知、消息推送平台，您可以通过控制台或接口操作，将信息无延时的推送给目标用户并支持多种提示方式。|
|细分目标用户|精细化目标用户分类，为目标用户打上画像标签，不论地理位置、是否活跃用户，还是各个版本用户均能准确定位。|
|运营数据全面监控|推送完成后，可及时查看推送效果，推送量、抵达量、点击量等关键运营数据一目了然，为您的运营提供充分数据支撑。|
|灵活的服务端接口|支持多种推送接口，包括全量、单个、批量推送等。方便业务结合自身需求灵活调用。提供Java、PHP、Python、Node.js等多种SDK，方便开发者使用。|


## 优势

| 功能 | 简介 | 
| :---: | :---- |
|极速接入|2 分钟极速接入推送服务，与数亿移动智能终端建立稳定的长连接|
|精准触达|多维度传递价值信息，每天可发送百亿级的通知/消息，精确抵达目标用户|
|接口灵活|开放推送能力，提供多种语言 API ，包括Java/PHP等，业务自由集成|
|全面监控|实时监控通知/消息的抵达用户量、转化量、转化率，推送效果一目了然|

## 客户案例

![](https://mc.qcloudimg.com/static/img/35bf4424ea924e85dd6773fba6f46f73/image.png)
![](https://mc.qcloudimg.com/static/img/1f993f9b49cb8e40b3576988c3654b87/image.png)
![](https://mc.qcloudimg.com/static/img/ae023ffed0c646a12a1ccde22ec6c2d4/image.png)
![](https://mc.qcloudimg.com/static/img/e4907596029230734e98355594196347/image.png)
![](https://mc.qcloudimg.com/static/img/c2d912a3a69317fdbbe38968f01bc8f3/image.png)
![](https://mc.qcloudimg.com/static/img/6b9207845b08dbf69923d095b705cf39/image.png)


## FAQ

1、iOS SDK 中有没有使用热更新或者私有接口？

Messaging SDK 没有使用过热更新或私有接口，不会影响苹果审核。

2、推送数量/推送频率限制？

推送数量无限制。推送频率上，仅全量广播限频为每 3 秒一次，其他推送行为不限频。

3、对单个设备，保存多少条离线信息？保存时间？

离线消息 Android 最多保存 2 条，iOS 最多保存 1 条；保存时间最多 72 小时。

4、标签方面限制？

单个设备最多设置 100 个标签，单个 App 全局最多可以有 10000 个不同的标签。


5、当第一次注册成功后，没有反注册，以后使用还需要注册吗？

不需要，只要没反注册，就不需要再次注册


6、应用关闭或结束进程后，还能收到推送消息吗？

Messaging 主要依赖 service 进行消息的收发，杀死进程之后 service 也被杀死，只能等待 service 被拉活或重启 App 才可以收到推送。若手机中有其他接入 Messaging 的 App 被打开，则可以利用其他 App 的 service 接收消息，但共享 service 通道也受手机 ROM 限制，无法保证百分之百的成功率。

7、设备注册为什么收不到回调信息？

注册操作中，后台只可能有三种出错行为：

1. 不响应；
2. 返回错误格式的数据包；
3. 返回错误码。这三种行为终端应该都可以检测到并给出回调。

8、为什么我推送成功了，有了抵达量，点击量却等于 0 ？

iOS 点击量统计需要调用特殊代码，具体请参考 iOS 开发文档。

9、为什么会出现推送通知时，只有声音却没有文字信息的情况？

该问题与系统有很大关系，需要拿设备的 logcat 来进行特定分析。

10、token 与 Account 区别？

token 是一台设备（device）的标识，账号是一个用户（users）的标识。一个 token 只能绑定一个账号，多次绑定时，以最后一次为准。

11、账号在设备 A 上登录过，又在设备 B 上登录？给这个账号发信息会怎么样？

只要是没有注销，则两台设备都会收到。

12、标签与账号的区别？

标签是用于标识一个 token 或用户的一些属性，如广东省、男性、游戏玩家等。帐号是用户的账号，请勿用标签作为别名使用。

13、在应用列表中看到“覆盖设备数”，具体指的是什么？

是指该应用下处于注册状态的设备数/终端数，同时也是该应用在推送时可以覆盖到的最大设备数。终端若调用了 unregister 的接口，覆盖设备数会减少。

14、为什么在 Web 端推送出现服务器繁忙？

请先检查 token 以及所选推送环境是否正确，然后检查证书是否正确提交，若还出现相同错误可重新制作一份不带密码的证书提交再试。

15、推送过程中，非定时推送（立即推送）能否撤销？

不能，只有返回 push_id 的任务才可以做撤销操作。

16、推送后查看推送列表，已经推送完成了，状态却显示推送中，怎么办？

刷新再试试。

17、在推送时，如何向单个用户推送消息？

请参考开发手册，有关于“推送消息给单个设备”和“推送消息给单个账户或别名”的使用指南。

18、用户重连上线后收到多条 push 的顺序是怎样？

按照消息 ID 递增。客户端也是按照此规则收取消息，因此，收消息的顺序就是发消息的顺序。

19、我现在有安卓的用户和 iOS 的用户，那我 php 后台要写两个不同的接口分别推给安卓用户和 iOS 用户吗

需要调用两次推送接口，也可以把两个封装为一个。

20、如果定时 push 选择的是过去的时间，是不是不会 push 出去？

不是，选择过去的时间系统则会立刻发送。

