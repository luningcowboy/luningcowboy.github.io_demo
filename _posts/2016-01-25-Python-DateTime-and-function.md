---
layout: post
title: Python Date,Time and function
category: Python
date: 2016-01-25
---
# 日期和时间的简单使用
*code*
{% highlight python linenos %}
#导入time模块
import time
#导入calendar(日历)模块
import calendar
#得到毫秒时间
ticks = time.time()
print ticks
#将毫秒时间转换为本地时间
localTime = time.localtime(ticks)
print localTime
#格式化时间
localTime = time.asctime(localTime)
print localTime
#输出指定月份的日历
cal = calendar.month(2016,1)
print cal
{% endhighlight %}
# 函数
{% highlight python linenos %}
#格式
def function_name(param):
  "文档，函数介绍"
  sentence
  return [返回值]
{% endhighlight %}

*code*
{% highlight python linenos %}

#一个简单的输出函数
def printMSG(msg):
    print msg
printMSG("TestInfo")
#有返回值的简单函数
def add(num1,num2):
    return num1 + num2
print add(10,20)
def printinfo(name,age):
    print "Name:",name,",Age:",age

printinfo("八戒",500)
printinfo(age=200,name="唐僧")
#报错
#printinfo(age=600,"孙悟空")
#printinfo(name="孙悟空",600)
#有默认值的函数
def printinfo_02(name,age=20):
    print "Name:",name,",Age:",age
printinfo_02("小白龙")
printinfo_02("沙和尚",500)
printinfo_02("如来",age=1000)
#不定长参数的函数
'''
def function_name([forml_args,]*var_args_tuple):
    "文档"
    scentence
    return [返回值]
'''
def printinfo_03(arg1,*vartuple):
    print "out_put:",arg1
    for var in vartuple:
        print var
    print "Test End"
printinfo_03("Test",1,2,"abc","bbbccc")
#lambda表达式
sum = lambda num1,num2:num1 + num2
print sum(1,2)
print sum(10,12)
#内部函数
def func01(num1,num2):
    def inner1():
        return num1 * 2
    def inner2():
        return num2 * num2
    ret = inner1() + inner2()
    return ret
print func01(1,2)

#闭包
'''
3.x闭包
def counter():
    idx = 0
    def innerFunc():
        nonlocal idx
        idx += 1
        return idx
    return innerFunc
'''
def counter():
    idx = 0
    def innerFuc():
        innerFuc.idx += 1
        return innerFuc.idx
    innerFuc.idx = idx
    return innerFuc

c1 = counter()
a = c1()
print a
a = c1()
print a
#这也是一个闭包
def func02(num):
    def inner1():
        print inner2()
    def inner2():
        inner2.num = inner2.num + 2
        return inner2.num
    inner2.num = num
    return inner1,inner2
print "============================="
f1,f2 = func02(5)
f1()
f2()
f1()
print "============================="
{% endhighlight %}
