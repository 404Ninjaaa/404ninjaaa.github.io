---
title: PicoCTF (Cryptography)
time: 2025-07-11 13:48:00
categories: [cryptography]
tags: [cryptography]
image: /assets/posts/picoctf/icon.svg

---
Here, I will upload all the challenges related to cryptography from PicoCTF.

# Easy

## hashcrack
Description:
A company stored a secret message on a server which got breached due to the admin using weakly hashed passwords. Can you gain access to the secret stored within the server? Access the server using nc verbal-sleep.picoctf.net 51759

---

Flag: `picoCTF{UseStr0nG_h@shEs_&PaSswDs!_ce730f64}`

First hash
```
482c811da5d5b4bc6d497ffa98491e38
```
Second hash
```
b7a875fc1ea228b9061041b7cec4bd3c52ab3ce3
```
Final hash
```
916e8c4f79b25028c9e467f1eb8eee6d6bbdff965f9928310ad30a8d88697745
```

Solve
![1](/assets/posts/picoctf/cryptography/1.png)
![2](/assets/posts/picoctf/cryptography/2.png)
![3](/assets/posts/picoctf/cryptography/3.png)

<a href="https://crackstation.net/" target="_blank" rel="noopener noreferrer">CrackStation</a>

---
## EVEN RSA CAN BE BROKEN???
Description
This service provides you an encrypted flag. Can you decrypt it with just N & e?

---

Flag: `picoCTF{tw0_1$_pr!m33991588e}`

Given
```
N: 15928613151731081278533648010489352992316565972783091485210785708789704940974055218868029012357005248760013484239162547315231180707625399729360702389631798
e: 65537
cyphertext: 12327588305559078096577188615845070679859889639755618681872908049435596624315343497518932195430178842767071050215214885600402225442410728420332737221966807
```
Solution
```
from sympy import factorint
n = 15928613151731081278533648010489352992316565972783091485210785708789\
7049409740552188680290123570052487600134842391625473152311807076253997293607\
02389631798
factors = factorint(n)
print(factors)
```
```
from Crypto.Util.number import inverse, long_to_bytes
e = 65537
p = 79643065758655406392668240052446764961582829863915457426053928543948\
5247048702760943401450617850262438000674211958127365761559035381269986468035\
1194815899

n = 2 * p
ct = 1232758830555907809657718861584507067985988963975561868187290804943\
5596624315343497518932195430178842767071050215214885600402225442410728420332\
737221966807

phi = p - 1
d = inverse(e, phi)
m = pow(ct, d, n) 
print(long_to_bytes(m).decode())

```
Solution2

![4](/assets/posts/picoctf/cryptography/4.png)

<a href="https://www.dcode.fr/rsa-cipher" target="_blank" rel="noopener noreferrer">dcode</a>

---





