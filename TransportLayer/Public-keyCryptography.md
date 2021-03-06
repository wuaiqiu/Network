# public-key cryptography

**1.简介**

>公开密钥加密（英语：public-key cryptography，又译为公开密钥加密），也称为非对称加密（asymmetric cryptography），一种密码学算法类型，在这种密码学方法中，需要一对密钥，一个是私人密钥，另一个则是公开密钥。这两个密钥是数学相关，用某用户密钥加密后所得的信息，只能用该用户的解密密钥才能解密。如果知道了其中一个，并不能计算出另外一个。因此如果公开了一对密钥中的一个，并不会危害到另外一个的秘密性质。称公开的密钥为公钥；不公开的密钥为私钥。

如果加密密钥是公开的，这用于客户给私钥所有者上传加密的数据，这被称作为公开密钥加密（狭义）。例如，网络银行的客户发给银行网站的账户操作的加密数据。

如果解密密钥是公开的，用私钥加密的信息，可以用公钥对其解密，用于客户验证持有私钥一方发布的数据或文件是完整准确的，接收者由此可知这条信息确实来自于拥有私钥的某人，这被称作数字签名，公钥的形式就是数字证书。

```
RSA
RSA加密算法是一种非对称加密算法。在公开密钥加密和电子商业中RSA被广泛使用。比起DES和其它对称算
法来说，RSA要慢得多。
```

```
Diffie–Hellman 
迪菲-赫尔曼密钥交换（英语：Diffie–Hellman key exchange，缩写为D-H） 是一种安全协议。它可以让
双方在完全没有对方任何预先信息的条件下通过不安全信道创建起一个密钥。这个密钥可以在后续的通讯中
作为对称密钥来加密通讯内容，迪菲－赫尔曼密钥交换本身并没有提供通讯双方的身份验证服务，因此它很
容易受到中间人攻击。
```

<br>

**2.密码散列函数（英语：Cryptographic hash function）**，又译为加密散列函数、密码散列函数、加密散列函数，是散列函数的一种。它被认为是一种单向函数，也就是说极其难以由散列函数输出的结果，回推输入的数据是什么。这样的单向函数被称为“现代密码学的驮马”。这种散列函数的输入数据，通常被称为消息（message），而它的输出结果，经常被称为消息摘要（message digest）或摘要（digest）。一个理想的密码散列函数应该有四个主要的特性：
(1)对于任何一个给定的消息，它都很容易就能运算出散列数值
(2)难以由一个已知的散列数值，去推算出原始的消息
(3)在不更动散列数值的前提下，修改消息内容是不可行的
(4)对于两个不同的消息，它不能给与相同的散列数值

```
MD5
MD5消息摘要算法（英语：MD5 Message-Digest Algorithm），一种被广泛使用的密码散列函数，可以产
生出一个128位（16字节）的散列值（hash value），用于确保信息传输完整一致。1996年后被证实存在弱
点，可以被加以破解，对于需要高度安全性的数据，专家一般建议改用其他算法，如SHA-1。2004年，证实
MD5算法无法防止碰撞，因此无法适用于安全性认证，如SSL公开密钥认证或是数字签名等用途。
```

```
SHA-1
SHA-1（英语：Secure Hash Algorithm 1，中文名：安全散列算法1）是一种密码散列函数，美国国家安
全局设计，并由美国国家标准技术研究所（NIST）发布为联邦数据处理标准（FIPS）。SHA-1可以生成一个
被称为消息摘要的160位（20字节）散列值，散列值通常的呈现形式为40个十六进制数。2005年，密码分析
人员发现了对SHA-1的有效攻击方法，这表明该算法可能不够安全，不能继续使用
```

```
SHA-2
SHA-2，名称来自于安全散列算法2（英语：Secure Hash Algorithm 2）的缩写，一种密码散列函数算法
标准，由美国国家安全局研发，由美国国家标准与技术研究院（NIST）在2001年发布。属于SHA算法之一，
是SHA-1的后继者。其下又可再分为六个不同的算法标准，包括了：SHA-224、SHA-256、SHA-384、
SHA-512、SHA-512/224、SHA-512/256。
```

```
SHA-3
SHA-3第三代安全散列算法(Secure Hash Algorithm 3)，之前名为Keccak算法，设计者宣称在 Intel 
Core 2 的CPU上面，此算法的性能是12.5cpb(每字节周期数，cycles per byte)。不过，在硬件实做上
面，这个算法比起其他算法明显的快上很多。
```

<br>

**3.消息认证码（英语：Message authentication code，缩写为MAC）**，又译为消息鉴别码、文件消息认证码、讯息鉴别码、信息认证码，是经过特定算法后产生的一小段信息，检查某段消息的完整性，以及作身份验证。它可以用来检查在消息传递过程中，其内容是否被更改过，不管更改的原因是来自意外或是蓄意攻击。同时可以作为消息来源的身份验证，确认消息的来源。信息鉴别码不能提供对信息的保密，若要同时实现保密认证，同时需要对信息进行加密

密钥散列消息认证码（英语：Keyed-hash message authentication code，缩写为HMAC），又称散列消息认证码（Hash-based message authentication code），是一种通过特别计算方式之后产生的消息认证码（MAC），使用密码散列函数，同时结合一个加密密钥。它可以用来保证数据的完整性，同时可以用来作某个消息的身份验证。

![](../images/81.png)

<br>

**4.数字签名（又称公钥数字签名，英语：Digital Signature）**是一种类似写在纸上的普通的物理签名，但是使用了公钥加密领域的技术实现，用于鉴别数字信息的方法。数位签名了的文件的完整性是很容易验证的，而且数位签名具有不可抵赖性。

![](../images/82.png)
