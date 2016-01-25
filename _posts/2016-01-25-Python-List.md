---
layout: post
title: Python List
category: Python
date: 2016-01-25
---
# List

### 列表

*列表类似数组，列表中的每个元素都有一个自己的索引，类似数组中的下标，但是，列表更加灵活，能够进行许多非常有用的操作，而不局限于数组的索引。*

**注意：**
*列表的索引是从0开始的，更绝大部分语言中的数组一样。*

*code*
{% highlight python linenos %}
# _*_ coding:utf-8 _*_
#Python列表
#定义一个列表

list1 = ['lua','python',1,2]
list2 = [1,2,3,4,5]
list3 = ["a","b","c","d"]
#访问列表中元素的值
print list1[0]
print list2[3]
print list3[1]
print list1[-1]
#遍历列表
for val in list1:
    print val
#切片
print list1[:2]
print list1[0:1]
print list1[1:3]
print list1[-3:-1]
print list1[-3:0]#什么都不输出
#赋值
list1[1] = 'C++'
print list1[1]
list1[-1] = 'Java'
print list1[-1],list1[3]
#删除列表中的元素
del list1[2]
print list1,list1[2]
#列表的一些操作
print len(list2)
print list2 + list3#组成了一个新的列表
print list2 ,list3
print list2 * 4#组成了一个新的列表
print 'a' in list3
print 'a' not in list3
print 'z' in list3
print 'z' not in list3
list4 = list3
list5 = ['a','b','c','d']
list6 = ["a","b","c","d"]
print cmp(list2,list3)
print cmp(list3,list4)
print cmp(list5,list6)
print cmp(list6,list3)
print max(list2),max(list3),max(list1)
tuple1 = (1,2,3,4,5)
print tuple1
print list(tuple1)#将元组转换为list
#添加元素
#list5[4] = 'e'#错误的方法
print list5
list5.append('e')
print list5
list5.append('e')
print list5
print list5.count('e')
list5.extend(['f','g','h','i','j','k'])#这个是追加，加号产生的是一个新的list
print list5
print list5.index('e')#只能返回最先找到的对象的下标
print list5
list5.insert(5,'z')#插入
print list5
list5.pop()
print list5
list5.pop(5)#pop默认删除最后一个元素，传入索引，删除指定索引的元素
print list5
list5.remove('e')
print list5
list5.remove('e')#remove一次只能删除一个元素
print list5
list5.reverse()#将列表反向
print list5
list5.sort()#能传入一个函数，根据函数进行排序
print list5
{% endhighlight %}
