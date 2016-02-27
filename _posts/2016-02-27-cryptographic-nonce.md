---
layout: post
title: Cryptographic nonce
tags: [cryptography, nonce]
---

> *adjective*  
>     (of a word or expression) coined for or used on one occasion.   
>     "a nonce usage"

In cryptography, a nonce is an arbitrary value that may only be used **once**.  
It is often used in an authentication protocol to prevent **replay attacks**. 
For instance, nonces are used in **HTTP digest access authentication** to calculate an MD5 digest of the password.

![Nonce based authentication]({{ site.url }}/assets/cryptographic-nonce.png)

