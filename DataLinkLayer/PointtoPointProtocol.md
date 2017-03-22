														Point to Point Protocol
																		-----------点对点协议


## 1.点对点协议帧格式 ##

![](http://i.imgur.com/nuxHVv1.png)
(1) 标志：首部的标志符表示一个帧的开始，尾部的标志结束。规定为0x7E。
(2) 地址：因为是点对点，地址没有用，所以设为广播地址，0xFF
(3) 控制：规定为0x03，为保留字段，无意义
(4) 协议：定义数据字段中携带的数据类型
(5) 数据：长度可变，最大不超过1500B(MTU)
(6) 校验：FCS，用于CRC校验
注意：透明传输
字节填充：异步传输时转义字符为0x7D。填充方法：0x7E转变成(0x7D,0x5E),0x7D转变成(0x7D,0x5D)，ASCII码的控制字符，即小于0x20的字符，如0x03变成(0x7D,0x23)。

## 2.PPP(Point to Point Protocol) ##

在点对点连接传输多协议数据包提供一个标准方法，它是一个协议集合，是一种在串行链路上传输的IP数据包流行方法，被DSL大量广泛使用
LCP:建立,维护链路连接
NCP:网络状态会话
CCP:数据帧压缩
PAP，CHAP：用于认证

a.LCP（Link Control Protocol,）它是PPP协议的一个子集，在PPP通信中，发送端和接收端通过发送LCP包来确定那些在数据传输中的必要信息。用于建立,维护链路连接，LCP的控制代码

![](http://i.imgur.com/3GeMFs8.png)
b.NCP(Network Control Protocol)，即网络控制协议，在LCP完成链路建立和认证之后，该链路每端都进入网络状态，并使用一个或多个NCP进行网络层相关协商

c.CCP(Compress Control Protocol,压缩控制协议)在链路进入网络状态协商，用于压缩

d.PAP(Password Authentication Protocol，密码认证协议),用于控制认证，这种协议非常简单，一方请求，另一方发送一个密码，由于密码在PPP链路上加密传输，窃听者易捕获

e.CHAP(Challenge Handshake Authentication Protocol，查询-握手认证协议):安全性更高

