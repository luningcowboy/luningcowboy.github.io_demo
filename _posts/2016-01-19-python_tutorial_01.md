---
layout: post
title: 一些简单的基础知识
category: Python
date: 2016-01-19
---
# 一些基础知识

## 输出
*code*

{% highlight bash linenos %}
  print "Hello,Python"
{% endhighlight %}

## 多行语句
开发过程中，有的语句可能过长，那么，我们可能需要将这些语句分割到几行，下面就是python中如何实现.

{% highlight bash linenos %}
item_one = 10
item_two = 20
item_three = 30
total = item_one +\
  item_two +\
  item_three
{% endhighlight %}

*注意：当代码中有{},[]或()的时候不用使用连接符，程序也能识别跨行的代码。*

## 字符串的三种表现形式
- 单引号
- 双引号
- 三引号

*code*

{% highlight bash linenos %}
str1 = "python"
str2 = 'python'
str3 = """
  Python
  Python
  Python
"""
print str1
print str2
print str3
{% endhighlight %}

## 注释
- 单行注释
- 多行注释

*code*
{% highlight bash linenos %}
#这是单行注释
"""
这是多行注释，
这是多行注释，
这是多行注释
"""
'''
这是多行注释，
这是多行注释，
这是多行注释
'''
{% endhighlight %}
