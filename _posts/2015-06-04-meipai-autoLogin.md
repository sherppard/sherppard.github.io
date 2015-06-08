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

## 1.模拟浏览器的模块 

mechanize

pyv8

[上面两个模块的简单介绍](http://blog.sina.com.cn/s/blog_571b19a0010136xe.html)

Splinter : [简单介绍](http://blog.csdn.net/lanbing510/article/details/8489715)

selenium : [demo](http://www.cnblogs.com/fnng/p/3160606.html)[使用详解](http://www.cnblogs.com/fnng/p/3157639.html)


## 2.python调用其他py脚本返回值 

我的需求是这样的，python2.7下面运行不了python3的代码 

只能用调用的形式，而不能使用import的形式

使用os模块，调用系统命令执行
> os.system('python3 /home/xxx.py') 只能返回0

> os.popen('python3 /home/xxx.py') 这可以将脚本返回值进行导出

## 3.模拟http报文发送的模块  

### urllib2

- [一篇关于urllib2的demo](http://zhuoqiang.me/python-urllib2-usage.html#cookie)
- [一篇关于urllib2模块的详细解说_很透彻](http://www.cnblogs.com/daoluanxiaozi/p/3281706.html)
- [urllib2源码详解](http://xw2423.byr.edu.cn/blog/archives/794#viewSource)

- urllib 与 urllib2 为什么总是一起结伴出现？

urllib.urlencode() 是urllib2没有的方法，而这又是经常使用的功能

### [httplib](http://blog.csdn.net/wklken/article/details/7364360) 

- httplib 与 urllib 的区别

httplib比urllib更为底层，urllib很多实现都需要调用httplib  

ps: [httplib2详细使用指南](http://blog.csdn.net/five3/article/details/7079140)

[httplib详细使用指南](http://blog.csdn.net/five3/article/details/7078951)
  
### `urllib` in python3

urllib跟urllib2变成一个package urllib，而不是模块

```
import urllib.request
import urllib.parse

Request = urllib.request.Request(url) 
```

### 解析html数据的两个模块 htmllib 与 beautifulsoup

htmllib的使用远比Beautifulsoup要麻烦很多，htmllib一定要修改基类才能够按照自定义的标签提取方法

而BeautifulSoup只要很简单的几行代码就可以实现，htmllib要写很多代码才可以实现，所以不推荐使用htmllib

[BeautifulSoup 官方中文文档](http://www.crummy.com/software/BeautifulSoup/bs4/doc/index.zh.html)  

[BeautifulSoup 安装](http://my.oschina.net/u/1432929/blog/189660?p=1)  

[BeautifulSoup 入门](http://www.cnblogs.com/yupeng/p/3362031.html)

[BeautifulSoup 详解](http://blog.chinaunix.net/xmlrpc.php?r=blog/article&uid=22334392&id=3866984)

[BeautifulSoup 系列教材4篇](http://blog.csdn.net/abclixu123/article/details/25658227)

python3 BeautifulSoup 模块导入方法：

```
import bs4
from bs4 import BeautifulSoup
```

python2.7 BeautifulSoup 模块导入方法：

```
from bs4 import BeautifulSoup
```

[HTMLParser 官方文档](https://docs.python.org/3.4/library/html.parser.html#html.parser.HTMLParser.handle_starttag)

[HTMLParser 模块详解](http://www.cnblogs.com/yuxc/archive/2011/08/30/2159307.html)

[HTMLParser 实际案例](http://www.linuxidc.com/Linux/2014-05/101899.htm)

4.Oauth2.0认证机制


{% include image.html url="/media/2014-02-26-hello-cosette/cosette.jpg" width="100%" description="Amanda Seyfried as Cosette on the 2012 movie." %}

<table>
  
</table>

-----

made by sherpper，just for learn something!

