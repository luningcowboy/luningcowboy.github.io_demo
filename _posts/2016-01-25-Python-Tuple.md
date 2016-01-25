---
layout: post
title: Python Tuple
category: Python
date: 2016-01-25
---

# 元组
元组的功能与列表类似，不同的是元组中的元素不能够被修改，也就是说你完成了初始化，再想改就不行了。元组的表示方式是用'()'包围，其中的元素用逗号隔开。

*code*
{% highlight python linenos %}
# _*_ coding:utf-8 _*_
#Python元组
tup1 = ('lua','python',1,2)
tup2 = (1,2,3,4,5)
tup3 = 'a','b','c','d'
print tup1
print tup2
print tup3
#创建空元组
tup4 = ()
#元组中只有一个元素时,需要在元素后添加逗号，不然创建出来的不是元组
tup4 = (4)
print tup4
#正确的创建方式
tup4 = (4,)
print tup4
#访问元组
print tup1[0]
print tup2[1]
print tup3[3]
print tup1[-1]
#下面的操作会报错，因为，元组中的元素不能被改变
#tup1[2] = 'Java'
#切片
print tup1[:2]
print tup1[-4:]
print tup1[1:4]
#修改元组：元组中的元素是不可变的，要想改变的话，只能重新创建一个元组
tup4 = tup2 + tup3
print tup4
#删除元组
del tup4
#下面的操作会报错
#print tup4
#一些其他的操作
#得到元组的长度
print len(tup1)
#合并元组，生成一个新的元组
print tup2 + tup3
#将元组拷贝四分生成一个新的元组
print tup1 * 4
#判段元素是否在元组中
print 'lua' in tup1
print 'lua' not in tup1
#元组的遍历
for x in tup1:print x
#任意无符号的对象，以逗号隔开，默认为元组
#上面元组的第三种定义方式
tup4 = 1,2,3,4,5
print tup4
#关于元组的常用函数
print cmp(tup1,tup2)
tup5 = 1,2,3,4,5
#元组中的元素相同，返回值为0
print cmp(tup4,tup5)
#获得元组的长度
print len(tup4)
#得到元组中最大的值
print max(tup4)
#得到元组中最小的值
print min(tup4)
#将列表转换为元组
list1 = [1,2,3,4,5]
#这个方法，并不是说将列表变量改成了元组，而是，将
#列表中的元素拷贝了一份，生成了一个新的元组变量
tup6 = tuple(list1)
print list1
print tup6
{% endhighlight %}
