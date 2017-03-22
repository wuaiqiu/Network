													# NAT #


1.NAT(Network Address Translation)

NAT本质上是一种允许在互联网的不同地方重复使用相同的IP地址，包括基本NAT(basic NAT)与网络地址端口转换(Network Address Port Translation,NAPT)

basic NAT：

![](http://i.imgur.com/eQNCV9J.png)
NAPT:


![](http://i.imgur.com/OVfaeVp.png)

2.NAT过滤行为

a.独立于端口(以端口)
![](http://i.imgur.com/oEvYIf8.png)

b.对于依赖地址(以地址Y1)

![](http://i.imgur.com/sp2CDAz.png)

c.依赖于地址与端口(以地址X1与端口x1)

![](http://i.imgur.com/NuoBTay.png)
3.NAT穿越

应对在处于使用NAT设备之间的私有IP网络中的主机之间建立链接


(1)打孔(hole punching):只对独立于端口有用
![](http://i.imgur.com/YbnmDOx.png)

(2).STUN（Simple Traversal of UDP over NATs，NAT 的UDP简单穿越）
STUN是一种网络协议，它允许位于NAT（或多重NAT）后的客户端找出自己的公网地址，查出自己位于哪种类型的NAT之后以及NAT为某一 个本地端口所绑定的Internet端端口。这些信息被用来在两个同时处于NAT 路由器之后的主机之间建立UDP通信。

(3).TURN（Traversal Using Relays  around NAT）
TURN方式解决NAT问题的思路与STUN相似，也是私网中的VOIP终端通过某种机制预先得公网上的服务地址（STUN方式得到的地址为出口NAT上外部地址，TURN方式得到地址为TURN Server上的公网地址），然后在报文净载中所要求的地址信息就直接填写该公网地址。
