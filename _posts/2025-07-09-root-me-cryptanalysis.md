---
title: Root-me (Cryptanalysis) - Writeup
time: 2025-07-09 12:32:00
categories: [cryptography]
tags: [cryptography]
image: /assets/posts/root-me/icon.svg
---

A writeup for Root-me's cryptanalysis challenges.

## Encoding - ASCII
Flag: `2ac376481ae546cd689d5b91275d324e`

Decode the string.

Input
```
4C6520666C6167206465206365206368616C6C656E6765206573743A203261633337363438316165353436636436383964356239313237356433323465
```

CyberChef's Recipe
```
From_Hex('None')
```

Output
```
Le flag de ce challenge est: 2ac376481ae546cd689d5b91275d324e
```

## Encoding - UU
Flag: `ULTRASIMPLE`

Very used by the HTTP protocol

Get the validation password.

Input
```
B5F5R>2!S:6UP;&4@.RD*4$%34R`](%5,5%)!4TE-4$Q%"@``
```

[Output](https://www.browserling.com/tools/uudecode)
```
Very simple ;)
PASS = ULTRASIMPLE
```

s://md5decrypt.net/en/)
```
7ecc19e1a0be36ba2c6f05d06b5d3058 : weak
```
## Hash - DCC
Flag: `ilikethat`

Retrieve the password of the Administrator user from the information output by the secretsdump tool of the Impacket suite.

Input
```
Administrator:15a57c279ebdfea574ad1ff91eb6ef0c
```

Output
```
$ john --format=mscash --wordlist=rockyou.txt hash.txt
<...>
ilikethat        (Administrator)     
<...>
```
