---
layout: post
title: Python Directonary(字典)
category: Python
date: 2016-01-25
---
# 字典
字典，如果接触过其他高级语言的话(C++,Java)对字典应该不陌生，这里的字典与那些字典类似，但是，这里的字典没有类型限制，同一个字典中可以存储任意类型的值。共同之处就是字典中的元素是由键和值组成的。

*code*
{% highlight python linenos %}
# _*_ coding:utf-8 _*_
#字典的创建
dict1 = {'Alice':'1230','Beth':'1123','Cecil':'1452'}
dict2 = {'abc':456}
#这才是神奇之处
dict3 = {'aab':123,12:36,10.2:100.123}
#访问字典中的值
print dict3['aab']
print dict3["aab"]
print dict3[10.2]
print dict3[12]
#修改字典元素的值
dict3['aab'] = 321
print dict3
dict3['aab'] = "new value"
print dict3
#删除字典中的元素
del dict3['aab']
print dict3
#清空字典
dict3.clear()
#这时候字典这个变量还是存在的，输出是不会报错的
print dict3
del dict3
"""
#这个时候再输出，程序就会报错了
#print dict3
#同其他语言中的字典一样，键不能重复，定义字典的时候，
#如果，同一个键对应两个值的话，后出现的会被记住
"""
dict4 = {'a':1,'b':2,'c':3,'a':4}
print dict4
#常用函数
dict5 = {'a':1,'b':2,'c':3,'a':4}
#比较两个字典中的元素是否相同
print cmp(dict4,dict5)
print cmp(dict4,dict2)
#求字典中元素的个数
print len(dict4)
#将字典转换为一个字符串
str1 = str(dict4)
print type(str1)
print type(eval(str1))
#清除字典中所有的元素
dict4.clear()
print dict4
#浅拷贝
dict6 = dict5.copy()
print dict5,dict6
#生成一个字典[1,2,3,4](可是元组，也可是列表)为键值，‘a’为初始值
dict7 = dict5.fromkeys([1,2,3,4],'a')
print dict7
#得到指定键对应的值
print dict5.get('a')
#是否有某个键
print dict5.has_key('a')
#以列表返回元组数组，元组中是键值对儿，形式如下：
#[('a', 4), ('c', 3), ('b', 2)]
print dict5.items()
#得到键列表
print dict5.keys()
#得到值列表
print dict5.values()
#键不存在时，添加元素，并设置默认值，存在不会更改键对应的值
dict5.setdefault('z',8)
print dict5
#dic.updata(dic1)将dic1中有并且dic中也有的键对应的值更新到dic中
dict7 = {'a':1,'b':2,'c':3,'d':4}
dict8 = {'a':3,'d':20}
print dict7
dict7.update(dict8)
print dict7
{% endhighlight %}
