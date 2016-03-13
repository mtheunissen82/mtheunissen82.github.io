---
layout: post
title: Forgot sudo
tags: [linux, bash]
---

Don't you hate it when you execute a command and find out you dont have the approriate permissions...  
`$ sudo !!` to the rescue!

> $ cat some_unreadable_file  
> cat: some_unreadable_file: Permission denied  
>  
> $ sudo !!  
> sudo cat some_unreadable_file  
> Behold!!! The super secret contents of some_unreadable_file

The `!!` will substitute the most recent command and execute.

Alternatives to reach the same goal:  
- `$ sudo !-1`  
- type sudo and `Ctrl+P` to paste the most recent command
