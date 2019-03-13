# Learning-Python
近来想写一个包管理工具，故开始学习Python3基本语法，于此做简单记录。通篇内容学习自[RUNOOB.COM/Python3](http://www.runoob.com/python3/python3-tutorial.html)。

## 基本语法

### 注释

Python中单行注释以 `#` 开头。

```python3
#!/usr/bin/python3
 
# 第一个注释
# 第二个注释
 
'''
第三注释
第四注释
'''
 
"""
第五注释
第六注释
"""
print ("Hello, Python!") # 行后注释
```

### 行与缩进

python最具特色的就是使用缩进来表示代码块，不需要使用大括号 `{}`。
**python 须严格保持缩进正确性。**

```python3
if True:
    print ("True")
else:
    print ("False")
```

### 多行语句

Python 通常是一行写完一条语句，但如果语句很长，我们可以使用反斜杠(\)来实现多行语句，例如：

```python3
total = item_one + \
        item_two + \
        item_three
```


---
## 基本数据类型

Python 中的变量不需要声明。每个变量在使用前都必须赋值，变量赋值以后该变量才会被创建。

### 多个变量赋值

Python允许你同时为多个变量赋值。例如：

```python3
a = b = c = 1
```

您也可以为多个对象指定多个变量。例如：

```python3
a, b, c = 1, 2, "runoob"
```

### 数据类型

Python3 中有六个标准的数据类型：

- Number（数字）
- String（字符串）
- List（列表）
- Tuple（元组）
- Set（集合）
- Dictionary（字典）

#### Number

Python3 支持 int、float、bool、complex（复数）。

内置的 type() 函数可以用来查询变量所指的对象类型。

```python3

>>> a, b, c, d = 20, 5.5, True, 4+3j
>>> print(type(a), type(b), type(c), type(d))
<class 'int'> <class 'float'> <class 'bool'> <class 'complex'>

>>>a = 111
>>> isinstance(a, int)
True
>>>

```

isinstance 和 type 的区别在于：

- type()不会认为子类是一种父类类型。
- isinstance()会认为子类是一种父类类型。

#### 数值运算

```python3
>>>5 + 4  # 加法
9
>>> 4.3 - 2 # 减法
2.3
>>> 3 * 7  # 乘法
21
>>> 2 / 4  # 除法，得到一个浮点数
0.5
>>> 2 // 4 # 除法，得到一个整数
0
>>> 17 % 3 # 取余 
2
>>> 2 ** 5 # 乘方
32
```

#### 字符串

Python中的字符串用单引号 ' 或双引号 " 括起来，同时使用反斜杠 \ 转义特殊字符。

字符串的截取的语法格式如下：

> 变量[头下标:尾下标]

```python3
#!/usr/bin/python3
 
str = 'Runoob'
 
print (str)          # 输出字符串
print (str[0:-1])    # 输出第一个到倒数第二个的所有字符
print (str[0])       # 输出字符串第一个字符
print (str[2:5])     # 输出从第三个开始到第五个的字符
print (str[2:])      # 输出从第三个开始的后的所有字符
print (str * 2)      # 输出字符串两次
print (str + "TEST") # 连接字符串
```

### List

List（列表） 是 Python 中使用最频繁的数据类型。

列表可以完成大多数集合类的数据结构实现。列表中元素的类型可以不相同，它支持数字，字符串甚至可以包含列表（所谓嵌套）。

列表是写在方括号 [] 之间、用逗号分隔开的元素列表。

和字符串一样，列表同样可以被索引和截取，列表被截取后返回一个包含所需元素的新列表。

其用法基本与字符串一致，唯一不同点在于列表中元素可以改变。

```python3
>>>a = [1, 2, 3, 4, 5, 6]
>>> a[0] = 9
>>> a[2:5] = [13, 14, 15]
>>> a
[9, 2, 13, 14, 15, 6]
>>> a[2:5] = []   # 将对应的元素值设置为 [] 
>>> a
[9, 2, 6]
```

### Tuple

元组（tuple）与列表类似，不同之处在于元组的元素不能修改。元组写在小括号 () 里，元素之间用逗号隔开。

注：

> tup1 = ()    # 空元组
>
> tup2 = (20,) # 一个元素，需要在元素后添加逗号

### Set

集合（set）是由一个或数个形态各异的大小整体组成的，构成集合的事物或对象称作元素或是成员。

基本功能是进行成员关系测试和删除重复元素。

可以使用大括号 { } 或者 set() 函数创建集合，注意：创建一个空集合必须用 set() 而不是 { }，因为 { } 是用来创建一个空字典。

```python3
#!/usr/bin/python3
 
student = {'Tom', 'Jim', 'Mary', 'Tom', 'Jack', 'Rose'}
 
print(student)   # 输出集合，重复的元素被自动去掉
 
# 成员测试
if 'Rose' in student :
    print('Rose 在集合中')
else :
    print('Rose 不在集合中')
 
 
# set可以进行集合运算
a = set('abracadabra')
b = set('alacazam')
 
print(a)
 
print(a - b)     # a 和 b 的差集
 
print(a | b)     # a 和 b 的并集
 
print(a & b)     # a 和 b 的交集
 
print(a ^ b)     # a 和 b 中不同时存在的元素
```

### Dictionary

```python3
dict = {}
dict['one'] = "1 - 菜鸟教程"
dict[2]     = "2 - 菜鸟工具"
 
tinydict = {'name': 'runoob','code':1, 'site': 'www.runoob.com'}
 
 
print (dict['one'])       # 输出键为 'one' 的值
print (dict[2])           # 输出键为 2 的值
print (tinydict)          # 输出完整的字典
print (tinydict.keys())   # 输出所有键
print (tinydict.values()) # 输出所有值
```

### Python数据类型转换

|函数|描述|
|:--:|:--:|
|int(x [,base])            |将x转换为一个整数                 |
|float(x)                  |将x转换到一个浮点数                |
|complex(real [,imag])     |创建一个复数                    |
|str(x)                    |将对象 x 转换为字符串              |
|repr(x)                   |将对象 x 转换为表达式字符串           |
|eval(str)                 |用来计算在字符串中的有效Python表达式,并返回一个对象|
|tuple(s)                  |将序列 s 转换为一个元组             |
|list(s)                   |将序列 s 转换为一个列表             |
|set(s)                    |转换为可变集合                   |
|dict(d)                   |创建一个字典。d 必须是一个序列 (key,value)元组。|
|frozenset(s)              |转换为不可变集合                  |
|chr(x)                    |将一个整数转换为一个字符              |
|ord(x)                    |将一个字符转换为它的整数值             |
|hex(x)                    |将一个整数转换为一个十六进制字符串         |
|oct(x)                    |将一个整数转换为一个八进制字符串          |

---


