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

Hash
```
4C6520666C6167206465206365206368616C6C656E6765206573743A203261633337363438316165353436636436383964356239313237356433323465
```

CyberChef's Recipe
```
From_Hex('None')
```

Solve
```
Le flag de ce challenge est: 2ac376481ae546cd689d5b91275d324e
```

## Encoding - UU
Flag: `ULTRASIMPLE`

Very used by the HTTP protocol

Get the validation password.

Hash
```
B5F5R>2!S:6UP;&4@.RD*4$%34R`](%5,5%)!4TE-4$Q%"@``
```

[Solve](https://www.browserling.com/tools/uudecode)
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

Hash
```
Administrator:15a57c279ebdfea574ad1ff91eb6ef0c
```

Solve
```
$ john --format=mscash --wordlist=rockyou.txt hash.txt
<...>
ilikethat        (Administrator)     
<...>
```
## Hash - DCC2

Flag: `ihatepasswords`

You can use hashcat or john

Hash
```
$DCC2$10240#Administrator#23d97555681813db79b2ade4b4a6ff25
```

Solve
```
Using Hashcat

echo '$DCC2$10240#Administrator#23d97555681813db79b2ade4b4a6ff25' > hash.txt

hashcat -m 2100 -a 0 hash.txt /usr/share/wordlists/rockyou.txt

$DCC2$10240#administrator#23d97555681813db79b2ade4b4a6ff25:ihatepasswords
```
```
Using John

echo '$DCC2$10240#Administrator#23d97555681813db79b2ade4b4a6ff25' > hash.txt

john --format=mscash2 --wordlist=/usr/share/wordlists/rockyou.txt dcc2.hash

ihatepasswords   (administrator)
```

## Hash - LM

Flag: `ADMIN!!`

Hash
```
d3bf255c530633b9aad3b435b51404ee
```

Solve
```
echo "d3bf255c530633b9aad3b435b51404ee" > hashfile.txt

hashcat -m 3000 -a 0 hashfile.txt /usr/share/wordlists/rockyou.txt

d3bf255c530633b9:ADMIN!!
```


