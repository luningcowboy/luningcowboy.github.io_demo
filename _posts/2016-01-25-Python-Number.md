---
layout: post
title: Python 数字
category: Python
date: 2016-01-25
---

# Python常用的一些数学方法

function|direction
--|--
ads(x)|返回数字的绝对值
ceil(x)|返回数字的上入整数:`math.ceil(4.1)==5`
cmp(x,y)| `x<y返回-1 x==y返回0 x>y返回1`
exp(x)|返回e的x次幂
fabs(x)|返回数字的绝对值
floor(x)|返回数字的下舍整数:`math.floor(5.9)==6`
log(x)|log函数，不多说
log10(x)|同上
max(x1,x2,...)|求最大数
min(x1,x2,...)|求最小数
modf(x)|返回x的整数部分与小数部分
pow(x,y)|幂
round(x[,n])|四舍五入
sqrt(x)|平方跟

*code*

{% highlight python linenos %}
print abs(-5)
print abs(-10.5)
print math.fabs(-5)
print math.fabs(-10.5)

print math.ceil(4.1)
print math.floor(4.9)
print round(4.1)
print round(4.6)

print cmp(1,1)
print cmp(1,2)
print cmp(2,1)

print max(1,2,3,4,5,6)
print min(1,2,3,4,5,6)

print math.modf(5.999)
print math.modf(-5.999)

print math.sqrt(25)

print math.pow(2,10)
{% endhighlight %}

## 随机数

function|direction
--|--
choice(seq)|从序列中挑选一个随机数
randrange([start,]stop[,step])|指定范围
random()|随机生成下一个实数(0,1)
seed([x])|改变随机数生成器的种子seed
shuffle(lst)|随机排列序列的元素(洗牌算法)
uniform(x,y)|随机生成下一个实数，范围[x,y]

*code*
{% highlight python linenos %}
import random
seq = [1,2,3,4,5,6,7,8,9,10,11,12,13]
print "test choice"
for i in seq:
    print random.choice(seq)
print "end tesst choice"

print "test randrange"
for i in range(0,50):
    print random.randrange(1,20,1)
print "end test randrange"

print "test random"
for i in range(0,20):
    ran = random.random()+0.05
    print int(ran*10)
    print ran
print "end test random"

print "test shuffle"
for i in range(0,5):
    random.shuffle(seq)
    print seq
print "end test shuffle"

print "test uniform"
for i in range(0,20):
    print random.uniform(1,5)
print "end test uniform"
{% endhighlight %}
