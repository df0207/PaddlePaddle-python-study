# 图像分类预习知识笔记
花了几天时间，在正式开营学习之前，先把课前预习知识和题目做了一下，首先复习了一下之前学的python基础。
## Python
1. Python是一种高级的、动态类型的多范例编程语言。
2. Python代码跟伪代码很相似，因为它可以使用很少的代码实现很强大的功能，同时又易于阅读。
3. 例如，这是经典的快速排序算法在Python中的实现：

```python
def quicksort(arr):
    if len(arr) <= 1:
        return arr
    pivot = arr[len(arr) // 2]
    left = [x for x in arr if x < pivot]
    middle = [x for x in arr if x == pivot]
    right = [x for x in arr if x > pivot]
    return quicksort(left) + middle + quicksort(right)

print(quicksort([3,6,8,10,1,2,1]))
# Prints "[1, 1, 2, 3, 6, 8, 10]"
```

### 1. 命令行中仔细检查Python版本
python --version
### 2.1 数字
1. 整数和浮点数可以像其他语言一样使用。
2. 请注意，与许多语言不同，Python没有一元的增量（x++）或减量（x--）运算符。
3. Python还具有用于复数的内置类型。
### 2.2 布尔
Python的逻辑运算符使用的是英语词语而非符号（&&，||等等）
False
True
### 2.3 字符串
Python对字符串有很好的支持 
字符串的各种运算方法函数
### 2.4 列表
列表的创建，赋值，方法，属性
x = xs.pop()      # Remove and return the last element of the list
### 2.5 列表的切片
切片： 除了一次访问一个列表元素，Python还提供了简洁的语法来访问子列表。这称为切片：
列表的索引和切片知识
### 2.6 循环
1. 循环遍历列表的元素
2. 如果要访问循环体内每个元素的索引，请使用内置enumerate函数
for循环  列表生成式
### 2.7 词典
1. 字典存储（键，值）对，类似于Map
2. 很容易遍历字典中的键
3. 如果要访问键及其相应的值，请使用以下items方法
print(d.get('monkey', 'N/A'))  # Get an element with a default; prints "N/A"
print(d.get('fish', 'N/A'))    # Get an element with a default; prints "wet"
d['fish'] = 'wet'     # Set an entry in a dictionary
del d['fish']         # Remove an element from a dictionary
### 2.8 集合
1. 集合是只包含不同元素且无序的
2. 在集合上进行迭代与在列表上进行迭代具有相同的语法；但是，由于集合是无序的，因此无法假设访问集合元素的顺序
animals.add('cat')        # Adding an element that is already in the set does nothing
animals.remove('cat')     # Remove an element from a set
for idx, animal in enumerate(animals):  取索引
### 2.9 元组
元组是（不可变的）有序值列表。元组在很多方面都类似于列表。最重要的区别之一是元组可以用作字典中的键和集合的元素，而列表则不能。
### 3.0 函数
Python函数是使用def关键字定义的。
### 4.0 类
在Python中定义类的语法很简单：

```python
class Greeter(object):

    # Constructor
    def __init__(self, name):
        self.name = name  # Create an instance variable

    # Instance method
    def greet(self, loud=False):
        if loud:
            print('HELLO, %s!' % self.name.upper())
        else:
            print('Hello, %s' % self.name)

g = Greeter('Fred')  # Construct an instance of the Greeter class
g.greet()            # Call an instance method; prints "Hello, Fred"
g.greet(loud=True)   # Call an instance method; prints "HELLO, FRED!"
```
## python做题
复习了一下基础知识，做了三天python练习题，主要是一些用循环判断生成列表、字典，列表生成式，函数和类的一些应用。

## 机器学习的思考故事
看了一下关于飞桨2.0的说明和使用教程，大致了解怎么用，然后最后的预习内容是机器学习的思考故事的前两课，下面把学习的主要内容记录一下：
### 课节1: 机器学习与大数据
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210301010719515.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjY0MDgxMg==,size_16,color_FFFFFF,t_70#pic_center)

### 课节2: 机器学习的建模：深入理解机器如何学到？
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210301010731368.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjY0MDgxMg==,size_16,color_FFFFFF,t_70#pic_center)
