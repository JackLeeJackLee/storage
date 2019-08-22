[toc]

# 数据
## 变量

1. 变量名不能以数字开头
2. 保留字'False', 'None', 'True', 'and', 'as', 'assert', 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except', 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'return', 'try', 'while', 'with', 'yield'不能用作变量名

## 数据类型
Python3 中有六个标准的数据类型：  
Number（数字）
String（字符串）
List（列表）
Tuple（元组）
Set（集合）
Dictionary（字典）

Python3 的六个标准数据类型中：  
不可变数据（3 个）：Number（数字）、String（字符串）、Tuple（元组）；  
可变数据（3 个）：List（列表）、Dictionary（字典）、Set（集合）。 

## 数字
### 类型
Python3 支持 int、float、bool、complex（复数）。
其中int类似于Java中的BigInteger类型，它的长度不受限制
```python
>>> a, b, c, d = 20, 5.5, True, 4+3j
>>> print(type(a), type(b), type(c), type(d))
<class 'int'> <class 'float'> <class 'bool'> <class 'complex'>
```
此外还可以用 isinstance 来判断：
```python
>>>a = 111
>>> isinstance(a, int)
True
>>>
```
isinstance 和 type 的区别在于：

type()不会认为子类是一种父类类型。
isinstance()会认为子类是一种父类类型。

```python
>>> class A:
...     pass
... 
>>> class B(A):
...     pass
... 
>>> isinstance(A(), A)
True
>>> type(A()) == A 
True
>>> isinstance(B(), A)
True
>>> type(B()) == A
False
```

### 操作符
#### 算数运算符
\+加号  -减号  *乘号   /真正的除法   **幂运算  //地板除法
#### 比较操作符
< <= > >= == !=  
python还支持这种连续比较
```python
>>> 3>5<8
False
>>> 6>5<8
True
>>> 1<7<9
True
>>> 1<7<9<10
True
>>> 
```

#### 逻辑操作符
and or not  

python中存在短路  
对于 and 来说：  
如果第一个条件的结论为假，那么 and 前后两个条件组成的表达式计算结果一定为假，后面的条件计算机不会进行计算

对于 or 来说：  
如果第一个条件的结论为真，那么 or 前后两个条件组成的表达式计算结果一定为真，后面的条件计算机不会进行计算
```python
>>> def  a():
    print("a执行了")
    return True

>>> def b():
	print("b执行了")
	return False
>>> b ()and a()
b执行了
False
>>> a () or b()
a执行了
True
>>> 
```

#### 位操作符
运算符|描述                                                                                           |实例
-     |                                                         -                                     |-
&	  |按位与运算符：参与运算的两个值,如果两个相应位都为1,则该位的结果为1,否则为0	                  |(a & b) 输出结果 12 ，二进制解释： 0000 1100
\|    |按位或运算符：只要对应的二个二进位有一个为1时，结果位就为1。                                   |(a \| b)输出结果 61 ，二进制解释： 0011 1101
^	  |按位异或运算符：当两对应的二进位相异时，结果为1                                                |(a ^ b) 输出结果 49 ，二进制解释： 0011 0001
~     |按位取反运算符：对数据的每个二进制位取反,即把1变为0,把0变为1。~x 类似于 -x-1 	              |(~a ) 输出结果 -61 ，二进制解释： 1100 0011， 在一个有符号二进制数的补码形式。
\<<	  |左移动运算符：运算数的各二进位全部左移若干位，由"<<"右边的数指定移动的位数，高位丢弃，低位补0。| << 2 输出结果 240 ，二进制解释： 1111 0000
\>>   |右移动运算符：把">>"左边的运算数的各二进位全部右移若干位，">>"右边的数指定移动的位数           |a >> 2 输出结果 15 ，二进制解释： 0000 1111

#### 成员操作符

in:如果在指定的序列中找到值返回True，或者返回False  
not in:如果在指定的序列中没有找到值返回True，或者返回False


#### 身份操作符

is：is是判断两个表示符是不是引用自一个对象  
is not：is not是判断两个标识符是不是引用自不同对象

is与==的区别：  
is用于判断两个变量引用对象是否是同一个，==用于判断引用变量的值是否相等。引用对象是否是同一个，可以用C语言的地址来理解。

#### 优先级
优先级从上到下从左到右
| 优先级 | 运算符          |
| ------ | --------------- |
| 1      | **（幂运算）    |
| 2      | +x -x（正负号） |
| 3      | * / // +        |
| 4      | < <= > >= == != |
| 5      | not and or      |




### 数学函数

 函数            | 	返回值 ( 描述 )                                         
 -               | -
 abs(x)          | 返回数字的绝对值，如abs(-10) 返回 10                     
 ceil(x)         | 返回数字的上入整数，如math.ceil(4.1) 返回 5                  
 cmp(x, y)       | 如果 x < y 返回 -1, 如果 x == y 返回 0, 如果 x > y 返回 1。 Python 3 已废弃，使用 (x>y)-(x<y) 替换。
 exp(x)          | 返回e的x次幂(ex),如math.exp(1) 返回2.718281828459045         
 fabs(x)         | 返回数字的绝对值，如math.fabs(-10) 返回10.0                  
 floor(x)        | 返回数字的下舍整数，如math.floor(4.9)返回 4                  
 log(x)          | 如math.log(math.e)返回1.0,math.log(100,10)返回2.0            
 log10(x)        | 返回以10为基数的x的对数，如math.log10(100)返回 2.0           
 max(x1, x2,...) | 返回给定参数的最大值，参数可以为序列。                       
 min(x1, x2,...) | 返回给定参数的最小值，参数可以为序列。                       
 modf(x)         | 返回x的整数部分与小数部分，两部分的数值符号与x相同，整数部分以浮点型表示。 
 pow(x, y)       | x**y 运算后的值。                                            
 round(x [,n])   | 返回浮点数x的四舍五入值，如给出n值，则代表舍入到小数点后的位数。
 sqrt(x)         | 返回数字x的平方根。                                          

## 序列
### 简介
在Python中，最基本的数据结构为序列（sequence）。
序列中的每个元素都有编号，即其位置或索引，其中第一个元素的索引为0，第二个元素的索引
为1，依此类推。在有些编程语言中，从1开始给序列中的元素编号，但从0开始指出相对于序列
开头的偏移量。这显得更自然，同时可回绕到序列末尾，用负索引表示序列末尾元素的位置。  
列表，元组和字符串统称为序列，他们之间的的共同点：
- 都可以通过索引得到每一个元素。
- 默认索引值总是从0开始（python同样也支持负索引）
- 都可以通过分盘的方法得到一个范围被的元素的集合。
- 有很多共同的操作符（重复操作符、拼接操作符、成员关系操作符）

### 常用的内建方法（BIF）
1. list([iterable])

list()方法用于把一个可迭代对象转换为列表，所谓迭代，是重复反馈过程的活动，棋目的通常是为了接近并到达所需的目标或者结果。每一次对过程的重复被称为一次“迭代”，儿每一次迭代得到的结果会被用来作为下一次迭代的初始值
```python
>>> a = list()
>>> a
[]
>>> # 将字符串的每个字符迭代存放到列表中
>>> b = list("Wang Wang Wang")
>>> b
['W', 'a', 'n', 'g', ' ', 'W', 'a', 'n', 'g', ' ', 'W', 'a', 'n', 'g']
>>> # 将元组的每个元素迭代存放到列表中
>>> c = list((1,2,3,4,5,5,6))
>>> c
[1, 2, 3, 4, 5, 5, 6]
>>> c = list((1,(1,2,3),3,4,5,5,6))
>>> c
[1, (1, 2, 3), 3, 4, 5, 5, 6]
```

2. tuple([iterable])  

tuple()方法用于把一个可迭代对象转换为元组，具体用法和list()一样。

3. str(obj)  

str()将一个数或其他类型转换成一个字符串：
```python
>>> a = 5.99
>>> b = str(a)
>>> b
'5.99'
>>> c = str(5e15)
```

4. len(sub)

len()方法用于返回sub参数的长度：
```python
>>> string = "1234,1234"
>>> len(string)
9
>>> list1 = [1,2,3,4,5,6]
>>> len(list1)
6
>>> tuple1 = 1,2,3
>>> len(tuple1)
3
```

5. max(···)  

max()方法返回用于序列或者参数集合中的最大值，max（）参数是一个序列，返回值是该序列中的最大值，也可以是多个参数，那么max（）将返回这些参数中最大的一个：
```python
>>> a = [[1,2,3],[3,2,1]]
>>> max(a)
[3, 2, 1]
```

6. min(···)

用法和max（）一样，但效果相反

7. sum(iterable[,start])

sum()方法用于返回序列iterable的总和，可选参数start，如果是指该参数，表示从该下标开始加起

8.sorted(iterable,key=None,reverse=False)

sorted()用于返回一个排序的列表,详细见后面的高级排序

9.reversed(sequence)

reversed()方法用于返回你想迭代序列的值。与内建方法reverse（）的区别是，列表的内建方法是原地翻转，而reversed()是返回一个翻转后的迭代对象
```python
>>> a = [1,2,3,4,5,6,7]
>>> reversed(a)
<list_reverseiterator object at 0x0000027A04F6B788>
>>> a
[1, 2, 3, 4, 5, 6, 7]
```
10. enumerate(iterable)

enumerate()方法生成由二元组（元素数量为2的元组）构成的一个迭代对象，每个元组有可迭代参数的索引号及对应的元素组成的
```python
>>> string = "asd"
>>> for each in enumerate(string):
	print(each,end=',')

	
(0, 'a'),(1, 's'),(2, 'd'),
```

11. zip(iter1[,iter2[...]])

zip()方法用于返回由各个可迭代参数共同组成的元组
```python
>>> str1 = '123'
>>> str2 = '1234'
>>> a = zip(str1,str2)
>>> a
<zip object at 0x0000027A04F70AC8>
>>> for each in a:
	print(each,end=' ')

	
('1', '1') ('2', '2') ('3', '3') 
```


## 字符串
### 基本知识
1. 用单引号或者双引号引住
2. 单引号引住的字符串可以在内部插双引号，双引号同理
3. 单引号内部如果出现单引号或者其他反斜线在之前插入一个反斜线转义，双引号同理
4. 如果一个字符串内有多条反斜杠在字符串前加一个r字母可以自动添加反斜线，变为原始字符串
	`string = r"a\a\a\a\a\"`
5. 字符串不能以\结尾，原始字符串也不能解决这个问题，若必须添加在\之前添加\进行转义
	`string = "asdf\\"`
6. python中没有字符类型，字符用长度为1的字符串保存，字符与ASCLL码之间的转换用ord（），chr（）函数
```python
print( c + " 的ASCII 码为", ord(c))
print( a , " 对应的字符为", chr(a))
a 的ASCII 码为 97
101  对应的字符为 e
```

### 长字符串
1. 用三重引号引起了的内容的格式会保留

```python
"""
asdf
zxcv
"""
```
等价于

```python
'\nasdf\nzxcv\n'
```

### 分片
```python
string = "I love Xiuyue Wan"
string[0:6:1]
```
string[]中第一个参数为起始下标，第二个参数为结尾下标后一个的位置，第三个参数表示步长，如果为负则表示反向步长

```python
特殊情况
>>> string[::]
SyntaxError: invalid syntax
>>> string[0:6]
'I love'
>>> string[:6]
'I love'
>>> string[1:]
' love Xiuyue Wan'
>>> string[::1]
'I love Xiuyue Wan'
>>> string[:6:1]
'I love'
>>> string[0::1]
"I love Xiuyue Wan"
>>> string[:6:-1]
'naW euyuiX'
```

### 链接

由于加号会引起内存回收等一些列问题，所以常用join()方法和format()方法完成
1. ’+’ 号连接

用 ‘+’连接字符串应该是最基本的方式了，话不多说，直接上代码。

```python

>>> text1 = "Hello"
>>> text2 = "World"
>>> text1 + text2
'HelloWorld'

```

优点：容易记忆。
缺点：性能较差，因为 Python 中的字符串是不可变类型。用 “+” 号连接就相当于生成一个全新的字符串，生成字符串则需要重新申请内存，那么当用 ” + ” 连接非常多个字符串时，将会很耗费内存，可能造成内存溢出。
2、’,’连接成 tuple (元组)类型

Python 中用 ‘,’连接字符串，最终会变成 tuple 类型，代码如下：
```python
>>> text1 = "Hello"
>>> text2 = "World"
>>> text1 , text2
('Hello','World')
>>> type((text1, text2))
<type 'tuple'>
>>>
```

3、%s 占位符连接

这种功能比较强大，借鉴了C语言中 printf 函数的功能，如果你有C语言基础，看下文档就知道了。这种方式用符号“%”连接一个字符串和一组变量，字符串中的特殊标记会被自动用右边变量组中的变量替换：
```python
>>> text1 = "Hello"
>>> text2 = "World"
>>> "%s%s"%(text1,text2)
'HelloWorld'
```
4、空格自动连接
```python
>>> "Hello" "Nasus"
'HelloNasus'
```
值得注意的是，不能直接用参数代替具体的字符串,否则报错，代码如下：
```python
>>> text1="Hello"
>>> text2="World"
>>> text1 text2
  File "<stdin>", line 1
    text1 text2
            ^
SyntaxError: invalid syntax
```

5、’*’ 连接

这种连接方式就是相当于 copy 字符串，代码如下：
```python
>>> text1="nasus "
>>> text1*4
'nasus nasus nasus nasus '
>>>
```

6、join 连接

利用字符串的函数 join。这个函数接受一个列表或元组，然后用字符串依次连接列表中每一个元素：
```python
>>> list1 = ['P', 'y', 't', 'h', 'o', 'n']
>>> "".join(list1)
'Python'
>>>
>>> tuple1 = ('P', 'y', 't', 'h', 'o', 'n')
>>> "".join(tuple1)
'Python'
```

每个字符之间加 “|”
```python
>>> list1 = ['P', 'y', 't', 'h', 'o', 'n']
>>> "|".join(list1)
'P|y|t|h|o|n'
```

7、 多行字符串拼接 ()

Python 遇到未闭合的小括号，自动将多行拼接为一行,相比三个引号和换行符，这种方式不会把换行符、前导空格当作字符。
```python
>>> text = ('666'
 '555'
 '444'
 '333')
>>> print(text)
666555444333
>>> print (type(text))
<class 'str'>
```

总结：上述七种方式，我们在开发中最常用的就是”+”和”join”这两种方式。加号连接效率低是在连续进行多个字符串连接的时候出现的，如果连接的个数较少，加号连接效率反而比 join 连接效率高。

### 内置方法
1. casefold（)方法将字符串的所有字符变为小写

```python
>>> string = "ASDF"
>>> string.casefold()
'asdf'
```
2. count(sub[,start[,end]])，查找sub子子字符串出现的次数（[]为可选参数）

```python
>>> string.count('as',0,9)
2
>>> string.count('as',0)
4
>>> string.count('as')
4
>>> string.count('as',,9)
SyntaxError: invalid syntax
>>> string.count('as',,)
SyntaxError: invalid syntax
```
3. find(sub[,start[,end]])与find(sub[,start[,end]])用来查找某个字符串在该字符串中的位置。如果找到了，则返回值是第一个字符的索引值；如果找不到，则find返回-1，而index（）方法会抛出异常

```python
>>> string = "I love Xiuyue Wan"
>>> string.find("love")
2
>>> string.find("good girl")
-1
>>> string.index("love")
2
>>> string.index("good boy")
Traceback (most recent call last):
  File "<pyshell#50>", line 1, in <module>
    string.index("good boy")
ValueError: substring not found
```
4. join(sub)以字符串为分隔符，插入到sub中所有的字符之间

```python
>>> "a".join("bbbbb")
'babababab'
```
参数可以是列表也可以是列表元组字典集合，但是集合不能保证拼接的顺序
```python
列表
>>> str1 = 'qqq'
>>> str2 = 'www'
>>> ''.join([str1,str2])
'qqqwww'
元组
>>> ''.join(('asdf','zxcv'))
'asdfzxcv'
字典
>>> ''.join({'asdf':1,'zxcv':2})
'asdfzxcv'
集合
>>> ''.join({'asdf','zxcv'})
'asdfzxcv'
>>> ''.join({'asdf','zxcv','uiop','fghj'})
'fghjuiopasdfzxcv'
```
5. replace(old,new[,count])
将字符串中的old字字符串替换成new子字符串，如果count值给定，则替换不超过count次

```python
>>> string = "I is dd"
>>> string.replace('is','am')
'I am dd'
```
6.split(sep=None,maxsplit=-1)不带参数默认是一空格为分隔符切开字符串，如果maxsplit参数有设置，则仅分隔maxsplit个子字符串，返回切片后的子字符串拼接的列表

###格式化
1. format()方法，既接受位置参数又接受关键字参数，二者均传递到一个叫做replacement字段。而这个replacement字段在字符串内有大括号{}表示

```python
>>> "{0},{1},{2}".format("qqq","www","eee")
'qqq,www,eee'
>>> "{a},{b},{c}".format(a="qqq",b="www",c="eee")
'qqq,www,eee'
```
位置参数和关键字参数一起使用时，未知参数必须在关键字参数之前，否则会报错
```python
>>> "{0},{b},{c}".format("qqq",b="www",c="eee")
'qqq,www,eee'
>>> "{a},{b},{0}".format("qqq",b="www","eee")
SyntaxError: positional argument follows keyword argument
```
{{}}相当于转义字符，可以输出类似{0},{1}这种组合
```python
>>> "{{0}}".format("不打印")
'{0}'
```
在替换域中，‘：’表示格式化符号的开始，‘.2f’表示四舍五入到小数点后两位的浮点数，注意是数字，如果后面参数输入为字符串会报错
```python
>>> "{0}：{1:.3f}".format("圆周率","3.1415926")
Traceback (most recent call last):
  File "<pyshell#5>", line 1, in <module>
    "{0}：{1:.3f}".format("圆周率","3.1415926")
ValueError: Unknown format code 'f' for object of type 'str'
>>> "{0}：{1:.3f}".format("圆周率",3.1415926)
'圆周率：3.142'
```
2. 格式化操作符：%

```python
>>> "%c"%97
'a'
>>> a = 97
>>> "%c"%a
'a'
>>> '%d转为16进制是：%X'%(124,124)
'124转为16进制是：7C'
```
格式化操作符的辅助指令
| 符号 | 含义                                               |
| ---- | -------------------------------------------------- |
| m.n  | m显示的最小宽度，n是小数点后的位数                 |
| -    | 结果左对齐                                         |
| +    | 在正数前面显示加号（+）                            |
| #    | 在八进制书前面显示‘0o’，在十六进制数前面显示‘0x64’ |
| 0    | 显示的数字前面填充‘0’代替空格                      |

## 列表


```python
>>> b = []
>>> a=[1,2,3,4,5]
>>> a[-1]
5
>>> a[0]
1
```
### 增
1.  append()将一个对象附加到列表末尾

```python
>>> a = [1,2,3]
>>> b = a
>>> b.append(4)
>>> a
[1, 2, 3, 4]
```

   

2.  copy()复制列表，常规的列表赋值操作实际上只是将另一个名称关联到列表，本质上两个列表名指向的是同一个列表，而copy()为真正的复制一份列表关联到对应的列表名

```python
>>> a = [1,2,3,4]
>>> b = a
>>> a[1] = 10
>>> a
[1, 10, 3, 4]
>>> b
[1, 10, 3, 4]

>>> a = [1,2,3,4]
>>> b = a.copy()
>>> a[1]=10
>>> a
[1, 10, 3, 4]
>>> b
[1, 2, 3, 4]
```

3.  extend()能够同时将多个值附加到列表末尾，为此可将这些值组成的序列作为参数提供给方法 extend 。换而言之，你可使用一个列表来扩展另一个列表。+号也能用于拼接字符串，但是和这种拼接的效率的效率相比要差得多，因为常规拼接必须使用a和b的副本创建一个新列表。通过切片操作可以获得效果。

```python
>>> a = [1, 2, 3]
>>> b = [4, 5, 6]
>>> a.extend(b)
>>> a
[1, 2, 3, 4, 5, 6]

>>> a = [1, 2, 3]
>>> b = [4, 5, 6]
>>> a[len(a):] = b
>>> a
[1, 2, 3, 4, 5, 6]
这虽然可行，但可读性不是很高。
```

4. insrt()用于将一个对象插入列表

```python
>>> numbers = [1, 2, 3, 5, 6, 7]
>>> numbers.insert(3, 'four')
>>> numbers
[1, 2, 3, 'four', 5, 6, 7]
与 extend 一样，也可使用切片赋值来获得与 insert 一样的效果。
>>> numbers = [1, 2, 3, 5, 6, 7]
>>> numbers[3:3] = ['four']
>>> numbers
[1, 2, 3, 'four', 5, 6, 7]
这虽巧妙，但可读性根本无法与使用 insert 媲美。
```

  

### 删
1.  clear()就地清空列表的内容 

2. remove() 用于删除第一个为指定值的元素。

```python
>>> x = ['to', 'be', 'or', 'not', 'to', 'be']
>>> x.remove('be')
>>> x
['to', 'or', 'not', 'to', 'be']
>>> x.remove('bee')
Traceback (innermost last):
File "<pyshell>", line 1, in ?
x.remove('bee')
ValueError: list.remove(x): x not in list
```

    remove 是就地修改且不返回值的方法之一。不同于 pop 的是，它修改列表，但不返回任何值。
### 改

1.  reverse（） 按相反的顺序排列列表中的元素

```python
>>> x = [1, 2, 3]
>>> x.reverse()
>>> x
[3, 2, 1]
```
 注意到 reverse 修改列表，但不返回任何值（与 remove 和 sort 等方法一样）。
 
2. sort（），用于对列表就地排序。就意味着直接对原列表进行修改，而不是返回排序后的列表的副本

```python
>>> x = [3,2,3,4,5,1]
>>> x.sort()
>>> x
[1, 2, 3, 3, 4, 5]
```

sort()方法并不会产生返回值，下面是经常犯的错误

```python
>>> x = [3,2,3,4,5,1]
>>> y = x.sort()
>>> print(y)
None
```


对列表进行排序，并保留原序列，如果直接将x赋值给y，这样实际上x，y指向的是同一个列表，没有办法保留原序列

```python
>>> x = [3,2,3,4,5,1]
>>> y = x
>>> y.sort()
>>> y
[1, 2, 3, 3, 4, 5]
>>> x
[1, 2, 3, 3, 4, 5]
>>>
```


正确的排序，并保留原序列

```python
>>> x = [3,2,3,4,5,1]
>>> y = x.copy()
>>> y.sort()
>>> y
[1, 2, 3, 3, 4, 5]
```


### 查

1. index()在列表中查找指定值第一次出现的索引，如果指定值不存在，会报错

2. pop 从列表中删除一个元素（末尾为最后一个元素），并返回这一元素。

```python
>>> a = [1,2,3,4,5]
>>> a.pop()
5
>>> a.pop(0)
1
>>> a
[2, 3, 4]
```
注意 pop 是唯一既修改列表又返回一个非 None 值的列表方法。

3.  count()计算指定的元素在列表中出现的次数 

### 分片
利用分片可以得到一个原来列表的==拷贝==。类表分片也可以简写，如果没有开始的位置，python会默认爱是位置是0。同样，如果要得到从指定索引值到列表末尾的所有元素，吧结束位置省去即可。如果没有放入任何索引值，而只有一个冒号，将得到整个列表的拷贝  
列表分片就是建立原列表的一个拷贝（或者说副本），所有如果你想对列表做出某些修改，但同时还向保持原来的那个列表，那么直接使用分片的方法来获取拷贝就很方便了。  
分片规则和字符串一致
```python
>>> a = [1,2,3,4,5]
>>> a[:]
[1, 2, 3, 4, 5]
>>> a[1:2]
[2]
>>> a[1:]
[2, 3, 4, 5]
>>> a[:5]
[1, 2, 3, 4, 5]
>>> 
>>> a[1:5:2]
[2, 4]
>>> a[::-1]
[5, 4, 3, 2, 1]
>>> a[4:1:-1]
[5, 4, 3]
>>> a[4:1:-2]
[5, 3]
```

### 高级排序
1. 要想获得排序结果，又想保留原序列，还可以使用BIF（Built-in Functions 内建函数）中的sorted()函数

```python
>>> x = [4, 6, 2, 1, 7, 9]
>>> y = sorted(x)
>>> x
[4, 6, 2, 1, 7, 9]
>>> y
[1, 2, 4, 6, 7, 9]
```
实际上，这个函数可用于任何可迭代的对象，但总是返回一个列表。
```python
>>> sorted('Python')
['P', 'h', 'n', 'o', 't', 'y']
```
2. sort()的高级应用
方法sort可以接受两个可选参数：key和reverse。这两个参数通常是俺名称指定的，称为关键字参数。   
参数key类似于c++语言中的sort参数中的Comp compfunction （但原理不一样），通过一个函数将列表中的值传入，然后返回一个值，根据返回值的大小进行排序
```python
>>> x = ['aaaa','a','aaaaaaaaaaaaaaa','aa']
>>> x.sort(key=len)
>>> x
['a', 'aa', 'aaaa', 'aaaaaaaaaaaaaaa']
>>> 
```
参数reverse，默认为False，当设置为True时，逆序排序。
```python
>>> x = ['aaaa','a','aaaaaaaaaaaaaaa','aa']
>>> x.sort(key=len,reverse=100)
>>> x
['aaaaaaaaaaaaaaa', 'aaaa', 'aa', 'a']
```
## 元组
元组和列表的最大的区别就是你可以任意修改列表中的元素，可以任意插入或者删除一个元素，而元组是不行的，元组是不饿不可改变的（像字符串一样）
### 创建和访问一个元组
创建元组时最关键的两个符号是小括号和逗号，创建列表时逗号不是必备的
```python
列表的创建
>>> a = [1,]
>>> a
[1]
>>> a = [1]
>>> a
[1]
元组的创建
>>> b = (1)
>>> b
1
>>> b = (1,)
>>> b
>>> q = "string1"
>>> w = "string2"
>>> e = "string3"
>>> a = 1,2,3
>>> a
(1, 2, 3)
>>> a = q,w,e
>>> a
('string1', 'string2', 'string3')
>>> 
(1,)
```
元组同样也支持分片,同时元组的切片也是元组
```python
>>> a = (1,2,3,4,5,6,7,8,9)
>>> b = a[1:5]
>>> b
(2, 3, 4, 5)
```
### 元组的用途
1. 他们用作映射中的键，以及集合中的成员，而列表不行
2. 有些内置函数和方法返回元组，这意味着像处理列表一样处理他们（需要使用元组没有的index和count方法时例外）


### 更新
同更新字符串的方法类似，通过拷贝现有的元组也可以对现有元组更新
```python
>>> a = (1,2,3,4,5,6,7)
>>> a = a[1:4] + a[3:5]
>>> a
(2, 3, 4, 4, 5)
```

### 删除
del
```python
>>> a = (1,2,3,4,5,6,7)
>>> del a
>>> a
Traceback (most recent call last):
  File "<pyshell#36>", line 1, in <module>
    a
NameError: name 'a' is not defined
```
## 字典
### 简介
字典是Python中唯一的映射类型。根据键可以轻松找到其对应的值  
在很多情况下，使用字典都比使用列表更合适，下面是一些常用用途：
- 表示棋盘的状态，其中每个键都是由坐标组成的元组
- 存储文件修改时间，其中的键为文件名
- 电话/地址簿
### 创建和使用字典
六种结果完全相同的字典创建方法
```python
>>> a = {'one':1,'two':2,'three':3}
>>> b = dict(one = 1,two = 2,three = 3)
>>> c = dict(zip(['one','two','three'],[1,2,3]))
>>> d = dict({'one':1,'three':3,'two':2})
>>> e = dict([('two',2),('one',1),('three',3)])
>>> f = dict((('two',2),('one',1),('three',3)))
>>> a == b == c == d == e == f
True
>>> 
```
直接通过键进行访问值
```python
>>> a = {'a':1,'b':2}
>>> a['a']
1
```
### 基本操作
- len(d)返回字典d包含的项（键-值对）数
- d[k]返回与键k相关联的值
- d[k] = v 将值v关联到键k
- del d[k]删除键为k的项
- k in d检查字典d是否包含键为看的项

### 内置方法
1. fromkeys()

fromkeys()方法用于创建并返回以新的字典，它有两个参数：第一个参数是字典的键；第二个参数是可选的，是传入键对应的值。如过不提供，那么默认是None
```python
>>> a = {}
>>> a.fromkeys((1,2,3))
{1: None, 2: None, 3: None}
>>> b = {}
>>> b.fromkeys((1,2,3),"HA HA")
{1: 'HA HA', 2: 'HA HA', 3: 'HA HA'}
>>> c = {}
>>> c.fromkeys((1,2,3),('a','b','c'))
{1: ('a', 'b', 'c'), 2: ('a', 'b', 'c'), 3: ('a', 'b', 'c')}
```

2. keys(),values()和items()

keys()用于返回字典中的键，values()用于返回字典中所有的值，items()用于返回字典中所有的键值对

3. get()和setdefault()   

get()方法提供了更宽松的方式去访问字典项，当键不存在时，get()方法并不会报错，而是返回一个None

```python
>>> a = {'z':1,'x':2,'c':3}
>>> a[1]
Traceback (most recent call last):
  File "<pyshell#23>", line 1, in <module>
    a[1]
KeyError: 1
>>> a['V']
Traceback (most recent call last):
  File "<pyshell#24>", line 1, in <module>
    a['V']
KeyError: 'V'
>>> a['z']
1
>>> a.get('z')
1
>>> a.get('v')
>>> print(a.get('v'))
None
```
setdefault()与get()很像，但是setdefault()在字典中找不到相应的键时会自动添加

4. copy()

copy()方法是复制字典

5. pop()和popitem()

pop()是给定键弹出值，而popitem()是弹出一个项
```python
>>> a = {'one':1,'two':2,'three':3}
>>> a.pop('two')
2
>>> a.popitem
<built-in method popitem of dict object at 0x0000022B1904CD18>
>>> a.popitem()
('three', 3)
>>> a
{'one': 1}
```

6. update()

update()方法， 使用一个字典中的项来更新另一个字典
```python
>>> a = {'one':1,'two':2,'three':3}
>>> b = {'one':'一','four':4}
>>> a.update(b)
>>> a
{'one': '一', 'two': 2, 'three': 3, 'four': 4}
```
对于通过参数提供的字典，将其项添加到当前字典中。如果当前字典包含键相同的项，就替换它。
可像函数 dict （类型构造函数）那样调用方法 update。这意味着调用update时，可向它提供一个映射、一个由键值对组成的序列（或其他可迭代对象）或关键字参数。

7. clear()

方法 clear 删除所有的字典项，这种操作是就地执行的（就像 list.sort 一样），因此什么都不
返回（或者说返回 None ）。
```python
>>> d = {}
>>> d['name'] = 'Gumby'
>>> d['age'] = 42
>>> d
{'age': 42, 'name': 'Gumby'}
>>> returned_value = d.clear()
>>> d
{}
>>> print(returned_value)
None
```
这为何很有用呢？看两个场景。下面是第一个场景：
```python
>>> x = {}
>>> y = x
>>> x['key'] = 'value'
>>> y
{'key': 'value'}
>>> x = {}
>>> y
{'key': 'value'}
>>> x
{}
```
下面是第二个场景：
```python
>>> x = {}
>>> y = x
>>> x['key'] = 'value'
>>> y
{'key': 'value'}
>>> x.clear()
>>> y
{}
```
在这两个场景中， x 和 y 最初都指向同一个字典。在第一个场景中，通过将一个空字典赋
给 x 来“清空”它。这对 y 没有任何影响，它依然指向原来的字典。这种行为可能正是你想要的，
但要删除原来字典的所有元素，必须使用 clear 。如果这样做， y 也将是空的，如第二个场景所示。

### 利用字典格式化字符串
format_map  
```python
>>> template = '''<html>
... <head><title>{title}</title></head>
... <body>
... <h1>{title}</h1>
... <p>{text}</p>
... </body>'''
>>> data = {'title': 'My Home Page', 'text': 'Welcome to my home page!'}
>>> print(template.format_map(data))
<html>
<head><title>My Home Page</title></head>
<body>
<h1>My Home Page</h1>
<p>Welcome to my home page!</p>
</body>
```

## 集合

### 简介
- 集合中的元素具有唯一性（自动去除重复值），稳定性（不能是列表字符串），无序性（不能通过下标进行访问）
- 集合有大括号包裹，各个元素由逗号相隔

### 创建集合
```python
>>> set1 = {1,3,2,4}
>>> set2 = set([1,2,3,4])
>>> set1 == set2
True
```
利用创建set的过程过滤重复项
```python
>>> a = [1,1,1,1,1,1,1]
>>> b = list(set(a))
>>> b
[1]
```

### 操作集合
- 使用迭代读取集合中的元素

```python
>>> a = [1,2,3,4,1,3,4,2,3,1]
>>> for i in set(a):
	print(i,end=' ')

	
1 2 3 4 
```
- 使用in和not in判断一个元素是否在集合中

```python
>>> b = set(a)
>>> 1 in b
True
>>> 9 in b
False
>>> 1 not in b
False
```
- 使用add方法添加元素，使用remove()方法可以删除集合中已知的元素

```python
>>> b.add(5)
>>> b
{1, 2, 3, 4, 5}
>>> b.remove(5)
>>> b.remove(99)
Traceback (most recent call last):
  File "<pyshell#82>", line 1, in <module>
    b.remove(99)
KeyError: 99
```
### 不可变集合

使用frozenset()函数可以使集合中的元素不能随意的正价或者删除
```python
>>> a = frozenset([111,2,2,3,2,3,4,6,8])
>>> a
frozenset({2, 3, 4, 6, 8, 111})
>>> a.add(1)
Traceback (most recent call last):
  File "<pyshell#85>", line 1, in <module>
    a.add(1)
AttributeError: 'frozenset' object has no attribute 'add'
```

## 文件
### 打开文件
使用open（）函数来打开函数  
open(file,mode='r',buffering = -1,encoding = None,errors = Nonemnewline = None,closefd = True, opener = None)  
第一个参数是传入是传入的文件夹名，如果只有文件夹名，不带路径的话，那么Python会在当前文件夹中去找到该文件并打开。  
第二个参数指定文件打开模式  


打开模式|执行操作 
---|---
'r' | 以制度方式打开文件(默认)
'w' | 以写入的方式打开文件，会覆盖已存在的文件
'x' | 如果文件已经存在，使用此模式打开将引发一场
'a' | 以写入模式打开，如果文件存在，则在末尾追加写入
'b' | 以二进制模式打开文件
't' | 以文本模式打开（默认）
'+' | 可读写模式（可添加到其他模式中使用）
'U' | 通用换行符支持


### 文件对象的方法


文件对象方法 | 执行操作
---|---
 close()           | 关闭文件
 read(size=-1)     | 从文件读取size个字符，当未给定size或者给定负值的时候，读取剩余的所有字符，然后作为字符串返回
 readline()        | 从文件中读取一整行字符串 
 write(str)        | 将字符串str写入文件
 writelines(seq)   | 像文件写入字符串序列seq。seq应该是一个返回字符串的可迭代对象
 seek(offset,from) | 在文件中地洞文件指针，从from（0代表文件其实位置，1代表当前位置，3代表文件末尾）偏移offset个字节 
 tell()            | 返回当前在文件中的位置

### 文件的关闭
close（）方法用于关闭文件。Python拥有垃圾回收机制，会在文件对象的引用计数将至零的时候自动关闭文件。再对文件进行了写入操作，那么应该在完成写入之后关闭文件。因为Python肯会缓存你写入的数据，如果中途发生意外，那么缓存的数据根本就不会写入文件中。
### 文件的读取和定位
 - read（）是按字节为单位读取，如果不设置参数，那么会全部读取出来，文件指针指向文件末尾
 - readline()方法用于在文件中读取一整行，就是从文件指针的位置向后读取，直到遇到换行符（\n）结束
 - tell（）方法可以返回单签文件指针的位置
 - seek（offset，from）方法可以调整文件指针的位置。两个参数表示从from（0代表文件起始位置，1代表当前位置，2代表文件末尾）偏移offset字节。将文件指针设置到文件的起始位置，使用seek（0，0）即可
 - list（f）直接将整个文件放入，按照换行符进行划分元素
 - 迭代读取文本文件中的每一行
    ```python
    f.seek(0,0)
    for esch_line in f:
        print(each_line)
    ```
### 文件的写入
写入文件必须用'w'或者'a',否则会报错，‘w’模式写入文件会将此前的文件内容全部删除，‘a’模式为追加模式
```python
f = open("XXX.txt",'w')
f.write('lllIIIlIlIlIlIIl')
f.close
```

### 文件系统(未完待续)

### pickle(未完待续)


# 条件、循环及其他语句

## 条件分支
```pythton
if 条件：
    条件为真（True）执行的操作
elif 条件：
    条件为真（True）执行的操作
else：
    条件为假（False）执行的操作
```
### 悬挂else
```c
if (hi>2)
    if(hi>7)
        print("asd");
else
    print("zxc")
虽然else是想和最外层的if匹配，但是实际上是和最近的if匹配的
```
python中要求缩进完全正确对齐，else与对齐的if或者elif匹配

### 条件表达式（三目表达式）
```python
if x<y:
    small = x
else:
    small = y
```
转化后为
```python
small = x if x<y else y  
```

## 循环


# 函数(未完待续)

# 异常处理(未完待续)

# 类和对象(未完待续)

# 魔法方法、特性和迭代器(未完待续)

# 模块和标准库(未完待续)