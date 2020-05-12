---
title: Python面向对象
tags:
  - Python面向对象
  - Python
categories:
  - Python基础
  - 面向对象
---


### 类

类：类（class）可以定义数据类型，决定我们如何使用该数据类型。我们用关键字 class 来创建类，一般建议将类的首字母大写：
``` bash
class Myclass:
  pass
```


### 类的实例
类的实例：我们需要为类创建实例，方法类似调用函数。
``` bash
class Myclass:
  pass
my_thing = Myclass()
```



### 面向对象编程
面向对象编程：上节我们学习的类的实例也可以称作为对象，这种通过定义类及创建对象的编程模式被称为“面向对象编程”。我们可以用 type() 来得到一个对象所在的类：
``` bash
class Myclass:
  pass
my_thing = Myclass()
print(type(my_thing))
```


### 类的变量
类的变量：我们可以在类中创建类的变量，类的变量对类的对象都一致。我们可以通过 对象名.变量名 的方式来获取变量的值。参见示例：
``` bash
class Myclass:
  name = "智能手机"
my_thing = Myclass()
print(my_thing.name)
```
输出：智能手机


### 方法
方法：我们之前见过一些 Python内置数据类型的方法，比如针对字典类数据的 get()。方法实质上是类中定义的函数，它至少有一个参数，其中第一个参数总是该调用方法的对象，习惯上我们将第一个参数命名为 self。
``` bash
class Myphone:
  def ring(self):
    print("叮铃铃铃……")
phone = Myphone()
phone.ring()
```
输出：叮铃铃铃……


### 方法的参数
``` bash
class Myphone:
  price = 4000
  def cal(self,discount):
    return self.price * discount
phone = Myphone()
print(phone.cal(0.8))
```
输出：3200.0


### __init__()
__init__()：我们还可以用 __init__() 方法来操纵对象。在创建类的时候，就可以用 __init__() 为类建立初始属性。
这样，每当建立类的对象时，就可以为对象的属性赋值。
``` bash
class Phone:
  def __init__(self,name,color):                  
    self.name = name  #用对象函数里的self调用第二参数
    self.color = color #用对象函数里的self调用第三参数
hua_wei = Phone("华为","黑色") #在对象外定义Phone的对象hua_wei,按顺序定义name，color（华为，黑色）
xiao_mi = Phone("小米","白色")  #在对象外定义Phone的对象xiao_mi,按顺序定义name，color（小米，白色）
print(hua_wei.name) # 华为——用Phone的对象 hua_wei 调用第一参数name
print(hua_wei.color) # 黑色——用Phone的对象 hua_wei 调用第二参数color
print(xiao_mi.name) # 小米——用Phone的对象 xiao_mi 调用第一参数name
print(xiao_mi.color) # 白色——用Phone的对象 xiao_mi 调用第二参数color

```


### __repr__()
__repr__()：当我们新创建一个对象，直接输出该对象时，默认返回的是该对象的内存地址:
```bash
class Phone:
    def __init__(self,name):
        self.name =name    
hua_wei = Phone("华为")
print(hua_wei.name)
# 输出：华为
print(hua_wei)
```
 输出： <__main__.Phone object at 0x106ebdb70>
以上为hua_wei的内存地址

对象的内存地址有时对我们用处并不大，如果在输出对象时，我们想看到特定信息。可以用 __repr__() 方法实现:
class Phone:
  def __init__(self,name):
        self.name =name    
  def __repr__(self):
    return "这是一部" + self.name +"手机"
hua_wei = Phone("华为")
print(hua_wei)
输出：这是一部华为手机

__repr__:只可以有一个对象，且只可输出字符串,可以这样想 __init__ 用来定义属性。则__repr__可用来输出