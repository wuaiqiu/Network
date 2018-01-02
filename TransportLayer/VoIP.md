#VoIP

**1.简介**

>VOIP ，即指在 IP 网络上使用 IP 协议以数据包的方式传输语音。使用 VOIP 协议，不管是因特网、企业内部互连网还是局域网都可以实现语音通信。一个使用 VOIP 的网络中，语音信号经过数字化，压缩并转换成 IP 包，然后在 IP 网络中进行传输。 

<br>

**2.呼叫信号协议**

>VoIP网络使用这些协议定位通讯另一端的设备，然后在发送方和接收方之间协商交流


```
SIP:会话发起协议(Session Initiation Protocol)是一个应用层的信令控制协议。提供了一种类似呼叫及呼叫号码的识别方式，呼叫者和接收者的授权，以及对于呼叫的转移。在识别呼叫者和接收方时，SIP的地址非常类似于PSTN（公众电话网）的电话号码，只不过SIP的地址看起来更像是email地址；具体格式是：sip:userID@getway.com。用户注册他们的地址到SIP服务器（被叫做“注册者”）上，然后呼叫者向服务器发送一次SIP请求。用户可以通过TCP或UDP协议发送SIP信息。
```

```
SDP：会话描述协议（Session Description Protocol或简写SDP）描述的是流媒体的初始化参数。
```

(A).用户 A 发起此呼叫，告诉 SIP 代理服务器要联系用户 B。
(B).SIP 代理服务器向 SIP 注册服务器发出请求，要求提供用户 B 的 IP 地址，并收到用户 B 的 IP 地址
(C).SIP 代理服务器转发用户 A 与用户 B 进行通信的邀请信息（使用 SDP），包括用户 A 要使用的媒体。
(D).用户 B 通知 SIP 代理服务器可以接受用户 A 的邀请，且已做好接收消息的准备。
(E).SIP 代理服务器将此消息传达给用户 A，从而建立 SIP 会话。
(F).用户创建一个点到点 RTP 连接，实现用户间的交互通信。



H.323:由国际电信联盟定义（ITU，International Telecommunications Union）H.323是一系列不同种类、完成不同任务的协议组合而成。这套协议中的一些成员有：
	H.225.0，用于建立连接
	H.332，用于大型会议
	H.235，用于提供安全和认证
	H.245，用于协商频道使用
	RAS，用于处理注册，管理和状态信息

<br>

**2.网关协议**

>一个网关，在它的普通意义上，是一个在两种网络间提供接口的设备。一个VoIP网关则将一个基于IP的网络连到普通公众电话网上，或者连到一个正常模拟电话上。VoIP网关有两个部分：媒体网关控制器（MGC，media gateway controller）；也被称作软交换机。媒体网关（MG，media gateway）。将VoIP网关中的电话控制逻辑和媒体处理逻辑分开。这些协议包括有：

>媒体网关控制协议（MGCP，Media Gateway Control Protocol）主要目的在于将网关功能分解成负责媒体流处理的媒体网关（MG），以及掌控呼叫建立与控制的媒体网关控制器（MGC）两大部分。同时MG在MGC的控制下，实现跨网域的多媒体电信业务。由于MGCP更加适应需要中央控管的通信服务模式，因此更符合电信营运商的需求。在大规模网络电话网中，集中控管是一件非常重要的事情，透过MGCP可利用MGC统一处理分发不同的服务给MG。

H.248（也被称作媒体网关控制器，或者Megaco，Media Gateway Controller）

<br>

**3.实时传输协议（RTP,Real-time Transport Protocol）以及相关协议**

```
   一旦MG从公共电话网回路中取得声音信号，RTP就负载着它穿过TCP/IP网络。RTP是一个用于通过IP网络传输声音和视频的标准。RFC 3550定义了它，它和SIP以及H.323一起协同工作。一个VoIP通话使用两个RTP流，一个方向一个。
   RTP一般使用高位端口号（16384-32767），但是对于RTP通讯来说却没有固定的标准端口。RTP自己也不提供质量控制服务（QoS，Quality of Service）。RTP和RTP控制协议（RTCP，RTP control protocol）一起工作，后者提供了对于RTP通讯的控制信息。RTP自行掌握对数据的传输。RTP能够收集相关信息（发送包数，丢包数，等等）以报告QoS结果。
   安全实时传输协议（SRTP，Secure Real Time Transport Protocol）保证了RTP数据的安全，认证，以及完整性。SRTCP（安全RTCP，Secure RTCP）则为RTPC提供了同样的安全服务。SRTP和SRTCP使用高级加密标准（以前被称作Rijndael），该标准已被美国政府采用以取代数据加密标准（DEC，Data Encryption Standard）。
```