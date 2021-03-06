# Symmetric-key algorithm

**1简介**

>对称密钥加密（英语：Symmetric-key algorithm）又称为对称加密、私钥加密、共享密钥加密，这类算法在加密和解密时使用相同的密钥，常见的对称加密算法有DES、3DES、AES

(1)在密码学中，分组加密（英语：Block cipher），又称分块加密或块密码，是一种对称密钥算法。它将明文分成多个等长的模块（block），使用确定的算法和对称密钥对每组分别加密解密。分组加密是极其重要的加密协议组成，其中典型的如DES和AES作为美国政府核定的标准加密算法，应用领域从电子邮件加密到银行交易转帐，非常广泛。

```
DES
数据加密标准（英语：Data Encryption Standard，缩写为 DES）是一种对称密钥加密块密码算法,DES现在
已经不是一种安全的加密方法，主要因为它使用的56位密钥过短。
```

密钥长度|56位
-------|---
块长度  |64位

```
3DES
三重数据加密算法（英语：Triple Data Encryption Algorithm，缩写为TDEA，Triple DEA），或称3DES
（Triple DES），是一种对称密钥加密块密码，相当于是对每个数据块应用三次数据加密标准（DES）算法。
由于计算机运算能力的增强，原版DES密码的密钥长度变得容易被暴力破解；3DES即是设计用来提供一种相对简
单的方法，即通过增加DES的密钥长度来避免类似的攻击，而不是设计一种全新的块密码算法。
```

密钥长度|168，112或56 位 
--------|-------
块长度	|64位

```
AES
高级加密标准（英语：Advanced Encryption Standard，缩写：AES），在密码学中又称Rijndael加密法，是美国联邦政府采用的一种区块加密标准。这个标准用来替代原先的DES，已经被多方分析且广为全世界所使用。2006年，高级加密标准已然成为对称密钥加密中最流行的算法之一。
```

密钥长度|128、192或者256比特
-----|-----------
块长度	|128位


(2)流加密（英语：Stream cipher），又译为串流加密、资料流加密，是一种对称加密算法，加密和解密双方使用相同伪随机加密数据流（pseudo-random stream）作为密钥，明文数据每次与密钥数据流顺次对应加密，得到密文数据流。实践中数据通常是一个位（bit）并用异或（xor）操作加密。

该算法解决了对称加密完善保密性（perfect secrecy）的实际操作困难。由于完善保密性要求密钥长度不短于明文长度，故而实际操作存在困难，改由较短数据流通过特定算法得到密钥流。

```
RC4
RC4（来自Rivest Cipher 4的缩写）是一种流加密算法，密钥长度可变。它加解密使用相同的密钥，因此也属于对称加密算法。RC4是有线等效加密（WEP）中采用的加密算法，也曾经是TLS可采用的算法之一。RC4由伪随机数生成器和异或运算组成。RC4的密钥长度可变，范围是[1,255]。RC4一个字节一个字节地加解密。
```