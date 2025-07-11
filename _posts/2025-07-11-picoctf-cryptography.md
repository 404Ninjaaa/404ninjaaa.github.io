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



