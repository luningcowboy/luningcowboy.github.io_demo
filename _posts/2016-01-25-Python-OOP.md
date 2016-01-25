---
layout: post
title: Python面向对象
category: Python
date: 2016-01-25
---

# Python面向对象
## 创建类

*模板*

{% highlight python linenos %}
class ClassName:
  '类的帮助信息'#类的文档
  class_suite#类体
{% endhighlight %}

*code*
{% highlight python linenos %}
# _*_ coding:utf-8 _*_

class Employee:
    '员工的基类'
    #员工的数量，类变量
    empCount = 0
    def __init__(self,name,salary):
        '''
        初始化员工的信息
        '''
        self.name = name
        self.salary = salary
        #改变员工的数量
        Employee.empCount += 1
    def displayCount(self):
        print "Total Employee %d"%Employee.empCount
    def displayEmployee(self):
        print "Name ",self.name,"Salary ",self.salary
#创建实例
emp1 = Employee("Jhon",1200)
emp2 = Employee("Sunny",2000)
#调用实例的方法
emp1.displayEmployee()
emp2.displayEmployee()
#调用类变量
print "Total emp:",Employee.empCount
{% endhighlight %}

## 给实例添加，删除，修改属性
*已经有的实例，我们可以给他添加新的属性，添加后也可以删除和修改。对于在类中声明的属性，我们也可以进行删除操作。*

*下面的代码是在上面的基础上进行的操作*

{% highlight python linenos %}
#属性的添加，删除和修改
emp1.age = 7
print emp1.age
emp1.age = 20
print emp1.age
#print emp2.age#添加属性并不能使该类的所有实例都有这个属性，而是我们添加属性的实例有了这个属性
del emp1.age
#print emp1.age#这句话报错，新添加的属性已经被删除
del emp1.name
#print emp1.name
{% endhighlight %}

## 类的内置属性
- __dict__:类的属性（包含一个字典，由类的数据属性组成）
- __doc__:类的文档字符串
- __name__:类名
- __module__:类所在的模块
- __base__:类所有的父类构成元素(包含了一个由父类组成的元组)

*code*

{% highlight python linenos %}
print "__doc__:",Employee.__doc__
print "__name__",Employee.__name__
print "__module__",Employee.__module__
print "__base__",Employee.__bases__
print "__dict__",Employee.__dict__
{% endhighlight %}


## 垃圾回收
Python的垃圾回收也是基于引用计数的.
*code*

{% highlight python linenos %}
class Point:
    def __init__(self,x=0,y=0):
        self.x = x
        self.y = y
    def __del__(self):
        class_name = self.__class__.__name__
        print class_name,"销毁"

pt1 = Point()
pt2 = pt1
pt3 = pt1
print id(pt1),id(pt2),id(pt3)
del pt1
del pt2
del pt3
{% endhighlight %}

## 类的继承

{% highlight python linenos %}
class subClassName(ParentClass1[,ParentClass2,...]):
  '类的文档'
  class_suite#类体
{% endhighlight %}

*code*

{% highlight python linenos %}
class Parent:
    parentAttr = 100
    def __init__(self):
        print "父类的构造方法"
    def parentMethod(self):
        print "调用父类方法"
    def setAttr(self,attr):
        Parent.parentAttr = attr
    def getAttr(self):
        print "父类的属性:",Parent.parentAttr
    def myMethod(self):
        print "父类方法:myMethond"
class Child(Parent):
    def __init__(self):
        print "调用子类构造方法"
    def chilldMethod(self):
        print "调用子类方法"
    def myMethod(self):
        print "子类方法:myMethod"

c = Child()
c.chilldMethod()
c.parentMethod()
c.setAttr(1000)
c.getAttr()

b = 100
#isinstance:判断一个对象是不是其或其子类的实例
#issubclass:判断一个类是不是另一个类的子类
print isinstance(c,Child)
print isinstance(c,Parent)
print isinstance(b,Parent)
print issubclass(Child,Parent)
#方法的重写
c.myMethod()class Parent:
    parentAttr = 100
    def __init__(self):
        print "父类的构造方法"
    def parentMethod(self):
        print "调用父类方法"
    def setAttr(self,attr):
        Parent.parentAttr = attr
    def getAttr(self):
        print "父类的属性:",Parent.parentAttr
    def myMethod(self):
        print "父类方法:myMethond"
class Child(Parent):
    def __init__(self):
        print "调用子类构造方法"
    def chilldMethod(self):
        print "调用子类方法"
    def myMethod(self):
        print "子类方法:myMethod"

c = Child()
c.chilldMethod()
c.parentMethod()
c.setAttr(1000)
c.getAttr()

b = 100
#isinstance:判断一个对象是不是其或其子类的实例
#issubclass:判断一个类是不是另一个类的子类
print isinstance(c,Child)
print isinstance(c,Parent)
print isinstance(b,Parent)
print issubclass(Child,Parent)
#方法的重写
c.myMethod()
{% endhighlight %}

## 基础重载方法
- `__init__(self[,args,...])`:构造函数
- `__del__(self)`:析构方法，删除一个对象
- `__repr__(self)`:转化为供解释器读取的格式
- `__str__(self)`:转化为适合人阅读的形式
- `__cmp__(self)`:对象比较

*code*

{% highlight python linenos %}
class Vector:
    def __init__(self,a,b):
        self.a = a
        self.b = b
    def __str__(self):
        return 'Vector(%d,%d)'%(self.a,self.b)
    def __add__(self, other):
        return Vector(self.a + other.a,self.b + other.b)

v1 = Vector(1,2)
v2 = Vector(3,5)
print "Add:",v1 + v2
print v1.__str__()
print v2.__str__()
{% endhighlight %}

## 类属性与方法
- 私有属性：*以两个下划线开头，表面这个属性是类的私有属性*
- 类的方法:*必须包含self ,并且self为第一个参数*
- 类的私有方法:*以两个下划线开头发方法为类的私有方法*

*code*

{% highlight python linenos %}
class JustCounter:
    __privateCount = 0
    publicCount = 0
    def count(self):
        self.__privateCount += 1
        self.publicCount += 1
        print self.__privateCount

counter = JustCounter()
counter.count()
counter.count()
print counter.publicCount
#print counter.__privateCount#报错
print counter._JustCounter__privateCount#能这样调用
{% endhighlight %}
