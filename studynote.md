# 有些话说
这是百度飞桨领航团举行的一次为期一周的零基础python训练营，免费学习，课程链接：
https://aistudio.baidu.com/aistudio/course/introduce/7073
六天分为两大块，两个老师分别讲了一部分，一部分讲基础，基本上百分之八十地方用的也就是这百分之二十的基础知识，后面主要讲面向对象、类这些提高知识，不是很好理解，需要多练习，有助教答疑，每天布置作业做，全程跟着直播上完，会有一些奖励，这是百度ai系列的入门基础课程，结营了也能看视频直接学习，只是没有直播跟着训练营的批改作业答疑一些奖励，后续一些深入课程也是免费的，会接着学习。笔记主要是为了记住一些后期还会需要理解的点

# 课程框架
python入门及环境配置
语法基础
函数
高级特性
面向对象
文件操作与常用模块的使用

## python入门及环境配置
起名法则

简单地理解，标识符就是一个名字，就好像我们每个人都有属于自己的名字，它的主要作用就是作为变量、函数、类、模块以及其他对象的名称

Python 中标识符的命名不是随意的，而是要遵守一定的命令规则，比如说：

标识符是由字符（A~Z 和 a~z）、下划线和数字组成，但第一个字符不能是数字。 标识符不能和 Python 中的保留字相同。 Python中的标识符中，不能包含空格、@、% 以及 $ 等特殊字符。 在 Python 中，标识符中的字母是严格区分大小写的

可变对象：list dict set

不可变对象：tuple string int float bool

## 语法基础
切片的语法：[起始:结束:步长] 字符串[start: end: step] 这三个参数都有默认值，默认截取方向是从左往右的 start:默认值为0； end : 默认值未字符串结尾元素； step : 默认值为1；

如果切片步长是负值，截取方向则是从右往左的

字符串常用函数

count 计数功能
显示自定字符在字符串当中的个数

find 查找功能
返回从左第一个指定字符的索引，找不到返回-1

index 查找
返回从左第一个指定字符的索引，找不到报错

split 字符串的拆分
按照指定的内容进行分割

replace 字符串的替换
从左到右替换指定的元素，可以指定替换的个数，默认全部替换

strip字符串标准化
默认去除两边的空格、换行符之类的，去除内容可以指定

字符串的变形
my_string.upper()
my_string.lower()
my_string.capitalize()

字符串的格式化输出
%
format
一种可读性更好的方法 f-string
** python3.6版本新加入的形式

list常用函数

添加新的元素
list1 = [‘a’,‘b’,‘c’,‘d’,‘e’,‘f’]
list1.append(‘g’) # 在末尾添加元素
list1.insert(2, ‘ooo’) # 在指定位置添加元素，如果指定的下标不存在，那么就是在末尾添加

list2 = [‘z’,‘y’,‘x’]
list1.extend(list2) #合并两个list list2中仍有元素

count 计数 和 index查找

删除元素
list1 = [‘a’,‘b’,‘a’,‘d’,‘a’,‘f’]
print(list1.pop(3))
list1.remove(‘a’)
列表生成式

生成器
通过列表生成式，我们可以直接创建一个列表。但是，受到内存限制，列表容量肯定是有限的。而且，创建一个包含100万个元素的列表，不仅占用很大的存储空间，如果我们仅仅需要访问前面几个元素，那后面绝大多数元素占用的空间都白白浪费了。

## 函数
函数是组织好的，可重复使用的，用来实现单一，或相关联功能的代码段。

函数能提高应用的模块性，和代码的重复利用率。你已经知道Python提供了许多内建函数，比如print()。但你也可以自己创建函数，这被叫做用户自定义函数。

函数代码块以 def 关键词开头，后接函数标识符名称和圆括号()。
任何传入参数和自变量必须放在圆括号中间。圆括号之间可以用于定义参数。
函数的第一行语句可以选择性地使用文档字符串—用于存放函数说明。
函数内容以冒号起始，并且缩进。
return [表达式] 结束函数，选择性地返回一个值给调用方。不带表达式的return相当于返回 None。

参数传递

位置参数
位置参数是最简单的一种函数调用的方式。位置参数须以正确的顺序传入函数、数量必须和声明时的一样。
def student_name_and_age(name, age):
print(‘姓名：%s 年龄 %s’ %(name, age))

缺省参数
调用函数时，缺省参数的值如果没有传入，则被认为是默认值。
def student_name_and_age(name, age=‘不愿透露’):
“设置默认参数”
print(‘姓名：%s 年龄 %s’ %(name, age))

可变参数
顾名思义，可变参数就是传入的参数个数是可变的，可以是1个、2个到任意个，还可以是0个。
可变参数允许你传入0个或任意个参数，这些可变参数在函数调用时自动组装为一个tuple。
def all_student_names(*names):
for name in names:
print(‘姓名：’, name)

关键字参数
关键字参数允许你传入0个或任意个含参数名的参数，这些关键字参数在函数内部自动组装为一个dict。
def student_info(name, age, **kw):
print(f’我的名字叫：{name},年龄：{age},其它信息：{kw}’)

命名关键字参数
如果要限制关键字参数的名字，就可以用命名关键字参数
def print_person_info(name, age, *, height, weight):
print(‘我的名字叫：’, name, ‘年龄：’, age,‘身高’, height, ‘体重’, weight)

参数的组合
在Python中定义函数，可以用必选参数、默认参数、可变参数、关键字参数和命名关键字参数，这5种参数都可以组合使用。但是请注意，参数定义的顺序必须是：必选参数、默认参数、可变参数、命名关键字参数和关键字参数。

变量的作用域和global变量
1.局部变量 作用域:在函数内
2.全局变量 作用域:在函数外
函数优先使用局部变量 在没有局部变量的情况下， 使用全局变量

lambda匿名函数
python 使用 lambda 来创建匿名函数。
lambda 只是一个表达式，函数体比 def 简单很多。
lambda 的主体是一个表达式，而不是一个代码块。仅仅能在 lambda 表达式中封装有限的逻辑进去。
lambda 函数拥有自己的命名空间，且不能访问自有参数列表之外或全局命名空间里的参数。
虽然 lambda 函数看起来只能写一行，却不等同于 C 或 C++ 的内联函数，后者的目的是调用小函数时不占用栈内存从而增加运行效率。

lambda 若干个输入参数 : 返回值的表达式
lambda arg1, arg2: arg1 + arg2

高阶函数

map / reduce
map()函数接收两个参数，一个是函数，一个是Iterable，map将传入的函数依次作用到序列的每个元素，并把结果作为新的Iterator返回。
reduce: 用传给 reduce 中的函数 function（有两个参数）先对集合中的第 1、2 个元素进行操作，得到的结果再与第三个数据用 function 函数运算，依此类推，最后得到一个结果。

sorted
排序也是在程序中经常用到的算法。无论使用冒泡排序还是快速排序，排序的核心是比较两个元素的大小。如果是数字，我们可以直接比较，但如果是字符串或者两个dict呢？直接比较数学上的大小是没有意义的，因此，比较的过程必须通过函数抽象出来。

装饰器
函数作为返回值
闭包
python中的闭包从表现形式上定义（解释）为：如果在一个内部函数里，对在外部作用域（但不是在全局作用域）的变量进行引用，那么内部函数就被认为是闭包(closure).

返回闭包时牢记一点：返回函数不要引用任何循环变量，或者后续会发生变化的变量。

装饰器
顾名思义，从字面意思就可以理解，它是用来"装饰"Python的工具，使得代码更具有Python简洁的风格。换句话说，它是一种函数的函数，因为装饰器传入的参数就是一个函数，然后通过实现各种功能来对这个函数的功能进行增强。

装饰器最大的优势是用于解决重复性的操作，其主要使用的场景有如下几个：
计算函数运行时间
给函数打日志
类型检查
当然，如果遇到其他重复操作的场景也可以类比使用装饰器。

偏函数
通过设定参数的默认值，降低函数调用的难度

模块
安装/卸载第三方模块

## 高级特性
主要以案例来讲类的基础
pop函数:
james_new.pop(0)移除列表中的第一个数据，并获得删除的数据

使用类的好处
降低复杂性-》更少的bug-》提高可维护行
类可以将数据与函数绑定在一起，使代码模块化
调用数据和函数，使用对象名.的方式，使代码更加优雅

面向对象的世界
代码通常称为类的方法，数据通常称为类的属性，实例化的对象称为实例

如何定义类
class Athlete:

第一部分：class定义类的关键字，Athlete符合python标识符命名规则，：表示类内容的开始
def init(self,a_name,a_dob=None,a_times=[]):

第二部分：def定义函数的关键字，init 方法是一个特殊方法会在实例化对象时自动调用，我们会在这个方法中对数据进行赋值。self作为类中函数的第一个参数，方便该方法调用该类的其他属性和方法。

第三部分：自定义的属性和方法

如何使用类
1.创建对象

对象名 = 类名(参数)

2.使用.调用类的方法和属性

对象.属性名

对象.方法名()

私用的属性和方法的定义：

在属性和方法名前加 __ 两个下划线

## 面向对象
这个是接着讲类和对象的知识
类的继承和多态 也是以案例需求来讲解，容易理解一点

定义：

class 子类名(父类名)：

情况1，如果子类有新增的属性，那么需要在子类__init方法中，调用父类的__init__

情况2，如果子类没有新增的属性,子类不需要写__init__方法

使用：
对象名 = 子类名(参数)

继承的好处：代码重用，升级功能（重写），新增功能（新的方法）

方法重写
子类方法与父类方法完全相同，子类若重写了父类的方法，则子类对象调用方法时就是调用的自己类中重新的方法。

多继承

## 文件操作与常用模块的使用
也是通过案例需求来理解知识点

文件处理模型
输入，处理，输出。

输入：读取4个队员的训练数据，读取4个文件

james.txt 2-34,3:21,2,34,2.45,3.01,2:01,2:01,3:10,2-22

sarah.txt 2:58,2.58,2:39,2-25,2:55,2:54,2.18,2:55,2:55

julie.txt 2.59,2.11,2:11,2:23,3-10,2-23,3:10,3.21,3-21

mikey.txt 2:22,3.01,3:01,3.02,3:02,3.02,3:22,2.49,2:38

处理：标准化数据，切分数据，top3（最快的3个时间）

输出：将每个人的信息打印在屏幕上显示
open() 为bif（内置函数），参数有多个，必须的是文件路径。 返回的一个文件对象。

file.readline(),读取文件中的一行。

open(‘work/data.txt’,‘w’)第一个参数文件路径，第二个参数打开文件的模式
f.write(‘this is file content’)参数为写入的内容 f.close()关闭文件

对象转JSON