---
layout: post
title: hjkl navigation 
tags: [vim, hjkl, navigation]
---
\<history>  
Vi was created on a ADM-3A terminal wich had the following keyboard layout.

![hjkl keyboard]({{ site.url }}/assets/hjkl-keyboard.jpg)

You can imagine why today in vim they still use hjkl navigation.  
\</history>  

After reading [this][2] post on **hjkl** navigation in vim I decided to try it for myself.
Soon I found out that, while the array keys where still available, too often I was using the arrows instead of hjkl.

To strengthen my attempt I decided to disable arrow navigation.

To disable arrow keys in normal, visual and select and operator-pending mode:  

{% highlight vim %}
map <up> <nop>  
map <down> <nop>  
map <left> <nop>  
map <right> <nop>  
{% endhighlight %}

To disable the arrow keys in insert mode:  

{% highlight vim %}
imap <up> <nop>  
imap <down> <nop>  
imap <left> <nop>  
imap <right> <nop>  
{% endhighlight %}

Good luck ;)

Sources:  
- [Why vim uses hjkl][1]  
- [Why arrow keys are not recommended][2]  

[1]: http://www.catonmat.net/blog/why-vim-uses-hjkl-as-arrow-keys/
[2]: http://superuser.com/questions/599150/why-arrow-keys-are-not-recommended-in-vim
