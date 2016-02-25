---
layout: post
title: vim save file... woops i forgot sudo 
tags: [linux, vim]
---

Everybody recognizes these moments... 
You open a file in vim.. start editing.. save file with `:w` and **KABOOM**! 

*E45: 'readonly' option is set (add ! to override)* 

Solution: 

> :w !sudo tee %
