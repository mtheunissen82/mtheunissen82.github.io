---
layout: post
title: expansion
tags: [linux, bash]
---

When using bash you may have heard of the word *expansion*. Expansion happens every time when you type a command and hit enter to execute it.
When you execute a command seven types of expansion will be performed in the following order:

1) brace expansion  
2) tilde expansion  
3) parameter & variable expansion  
4) arithmetic expansion  
5) command substitution  
6) word splitting  
7) pathname expansion  

## Brace expansion
Brace expansion is a mechanism by which arbitrary strings may be generated.
It consists of a optional preamble and/or postscript.  
In the below example 'a' is the preamble and 'c' is the postscript

> $ echo a{b,B}c  
> abc aBc

A usefull application if brace expansion is the creation of multiple directories.
In the below example for each month in the year 2016 a directory is created (might come in handy for accounting).

> $ echo 2016-0{1..9} 2016-{10..12}  
> 2016-01 2016-02 2016-03 2016-04 2016-05 2016-06 2016-07 2016-08 2016-09 2016-10 2016-11 2016-12

Or copy from one directory to another.

> $ cp -rf /long/path/to/certain/directory/{source,dest}

## Tilde expansion
Tilde expansion uses the tilde character '~' optionally followed by any character sequence matching a login name.  
If no login name is provided the home directory of the current user (a.k.a. $HOME) is substituted.

> $ echo ~  
> /home/current_user

If a valid login name is provided the home directory of the given login is substituted.

> $ echo ~mtheunissen  
> /home/mtheunissen

If a invalid login name is provided tilde expansion fails and simply prints the string as-is.

> $ echo ~unknown_login  
> ~unknown_login

Tilde expansion can also be used in variable assignment **directly** after the '=' sign (don't leave a blank space after the equal sign since in that case it won't work)

> $ ROOT_JUNK_DIR=~root/tmp/junk  
> $ echo $ROOT_JUNK_DIR  
> /root/tmp/junk

Other applications of tilde expansion:

> echo ~+  
> /path/equal/to/PWD/variable

> echo ~-  
> /path/equal/to/OLDPWD/variable

## Parameter & variable expansion

## Arithmetic expansion

## Command substitution

## Word splitting

## Pathname expansion
