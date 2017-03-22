										# IGMP #


1.广播

一般来说，只有UDP传输协议用户应用程序利用广播与组播，而TCP只能用于单播
广播:路由简单地将它接受到的任意报文副本转发除报文到达接口以外的其他接口，在ipv4中通过将主机部分全部设置为1


2.组播(IGMP,Internet Group Management Protocol)

组播(IGMP):路由简单地将它接受到的任意报文副本转发至感兴趣的主机，在ipv4中D类地址为组播地址

组播方式：

ASM(任意源组播):每个站选择愿意接受流量的组地址，而不考虑发送方
![](http://i.imgur.com/TWVwVRZ.png)

SSM(特定源组播):允许端终明确包含或排除从一组特定的发送方发送到一个组播组的流量

![](http://i.imgur.com/MZhVYHu.png)