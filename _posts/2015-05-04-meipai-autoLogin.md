---
layout: post
title: "新浪微博第三方登录的python实现"
quote: 来自一个朋友的项目，需要在美拍用微博账号授权登录
image: /media/2014-02-26-hello-cosette/cover.jpg
video: false
---

# 我再本项目的技术力量薄弱

我可能在python算是入门了，但是web那块我还是空白的，我只知道http协议的基本工作过程
对于细节方面，要用到很多没少用的模块，比如 httplib, urllib, urllib2, htmllib等

- 你可能需要Ipython

因为[ipython](http://www.ituring.com.cn/article/40324)是交互性的，测试代码非常方便，而且帮助功能也非常齐全。

- 究竟如何实现自动化，怎么实现最好?

1.模拟浏览器的模块 

mechanize

pyv8

[上面两个模块的简单介绍](http://blog.sina.com.cn/s/blog_571b19a0010136xe.html)

Splinter : [简单介绍](http://blog.csdn.net/lanbing510/article/details/8489715)

selenium : [demo](http://www.cnblogs.com/fnng/p/3160606.html)[使用详解](http://www.cnblogs.com/fnng/p/3157639.html)


2.python调用其他py脚本返回值 

我的需求是这样的，python2.7下面运行不了python3的代码 

只能用调用的形式，而不能使用import的形式

使用os模块，调用系统命令执行
> os.system('python3 /home/xxx.py') 只能返回0

> os.popen('python3 /home/xxx.py') 这可以将脚本返回值进行导出

3.模拟http报文发送的模块  

urllib2

- [一篇关于urllib2的demo](http://zhuoqiang.me/python-urllib2-usage.html#cookie)
- [一篇关于urllib2模块的详细解说_很透彻](http://www.cnblogs.com/daoluanxiaozi/p/3281706.html)
- [urllib2源码详解](http://xw2423.byr.edu.cn/blog/archives/794#viewSource)

httplib 与 urllib 的区别

httplib比urllib更为底层，urllib很多实现都需要调用httplib

urllib 与 urllib2 为什么总是一起结伴出现？

urllib.urlencode() 是urllib2没有的方法，而这又是经常使用的功能

python3下urllib跟urllib2变成一个package urllib，而不是模块


4.Oauth2.0认证机制


{% include image.html url="/media/2014-02-26-hello-cosette/cosette.jpg" width="100%" description="Amanda Seyfried as Cosette on the 2012 movie." %}

<table>
  
</table>

-----
Want to see something else added or report a bug? [Open an issue](https://github.com/camporez/camporez.github.io/issues/new).
