---
layout: post
title: grep carriage return
tags: [linux, bash, grep, carriage return]
---
Sometimes i find the need to search for files with (windows) CRLF line-ending.

> $ grep -rIl $'\r'

Explanation:  
**-r** recursive  
**-I** (capital i) skip binary files  
**-l** (lower l) suppress normal output (only print matching file names)  
The **$** sign in front of the regex enables the use of [C-style escape sequences][1].  
**\r** represents the carriage return control character  
Also notice the single quotes which enclose the regex.  

A use-case might be to recursivly transform all files from DOS to Unix line-endings:  

> $ grep -rIl $'\r' \| xargs dos2unix

[1]: https://en.wikipedia.org/wiki/Escape_sequences_in_C
