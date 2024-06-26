# Python

## 第一章 基本数据类型

### 代码格式
1.注释：这是第一个注释

```python
print("hello Python")  # 这是第二个注释
```

2.方式2：

```python
"""
    这是多行注释
    三对单引号或双引号
"""
'''
    这是三对单引号注释
'''
```

3.缩进：4个空格或一个Tab

```python
if True:
    print("True")
else:
    print("False")
```

### 标识符名称

1. 数字、字母、下划线组成。

- 变量：name,age,sex
- 函数名：小写：max(),min(),add()
- 类名：Student
- 区分大小写

2. 关键字：35个

help("for")

### 变量与常量

1. 变量：存储数据的标识符。 使用变量： 变量名 = 值

```python
lunk=8
print(lunk)
```

### 数据类型

#### 数值类型

##### int

```python
print(lunk,type(lunk))  # <class 'int'>
num2= 0b10101 # 二进制：0b
num3= 0o765   # 八进制：0o
num4= 0x87a   #十六进制：0x
print(num2,num3,num4)
```

##### 浮点型

```python
fnum=20.34
print(fnum,type(fnum))  # <class 'float'>

fnum1=1.993e4
print(fnum1)
```

###### 尾数不确定

```python
print(0.1+0.2)
print(round(0.1+0.2,1))
```

#### 布尔类型

True 1 ; 
False 0,0.0

#### 序列类型

##### 字符串

```python
""
''
""" """
''' '''
```

```python
name="张明"
age='22'
sex="男"
address="""大连\n市旅顺\t口区
     \'大连\"交通\\大学
        """
print(name,age,sex,address)
```

转义字符: \n,\t,\',\",\\

##### 列表

列表的操作

- list.append(x)：末尾添加元素x
- list.extend(l)：在列表末尾加入指定列表L的所有数据
- list.insert(0,x)：给指定位置插入元素，即在位置i插入x，其余元素一次向后退
- list.remove(x)：删除列表中第一个值为x的元素，若该元素不存在则出错
- list.pop([i])：删除列表中给定位置i处的元素，并返回该元素。不指定索引值返回最后一个元素
- list.clear()：删除列表中的所有元素，等价于del a[:]
- list.index()：返回列表中值为x的元素位置多有，不存在则出错
- list.count(x)：返回x在列表中出现的次数
- list.sort(key = None,reverse = False)：对列表中的元素排序，默认为升序
- list.reverse()：将列表中的元素的顺序反转
- list.copy()：返回列表的浅复制
  - 浅复制可以理解为一个指向列表的新的指针，类似于别名

##### 元组

- len(t)：返回元组的长度
- t + (6 , 7)：连接两个元组
- t * 3：复制元组
- 2 in t：检查元组中是否包含某个元素
- for i in t：遍历元组中的元素

#### 集合类型

##### 集合

集合里面只能放元组

##### frozenset

#### 空值

#### 类型转换

- int(x):x转换成整数
- float(x):x转换成浮点数
- str(x):x转换成字符串

##### 隐式转换

```python
x=10
y=3
z=x/y   # 执行除法运算，通过运算隐式转换了结果的类型
print(z,type(z))

float类型转换成int,只保留了整数部分，舍去了小数部分

print(int(3.15))
print(int(3.86))

int型转换成float

print(float(4554))

字符串转换成int或float:前提 字符串是数字组成

print(int("123")+int("332"))

进制之间的转换:hex()

print('十进制转换成十六进制',hex(2987))
```

#### 输入与输出

1. 输入 x = input("请输入您的信息") 无论输入什么数据，x都是字符串类型

```python
x = input("请输入您的姓名：")
print(x)

x = int(input("请输入您的年龄："))
print(x,type(x))
```

2. 输出:print(object,sep=' ',end='\n',file=sys.stdout)

- object:输出的对象，变量，变量之间的分隔符
- sep:分隔符，默认是空格
- end:结尾符号。默认是\n

```python
print('北京','大连',sep='\\',end='----->')
```

### 字符串常用操作

#### str.index("子串")

查找子串

返回子串的第一个字符的索引.找不到error

#### str.find("子串")

查找子串

找不到，返回-1

```python
str = "it is a good cat"
print(str.index("good"))
print(str.find("dd"))
```

#### str.replace("","")

替换字符，后者替换前者

返回新的字符串，字符串是不可变类型。

只能读取，不能修改。 

good 替换成 bad

```python
str_new = str.replace("good","bad")
print(str,"***",str_new)
```

#### str.split("分隔符")

返回一个列表

```python
str = "it is a good cat"
str_new2 = str.split(" ")
print(str_new2)
```

#### str.strip()

去掉字符串两端的空格

```python
str = "   it is a good dog   "
str_new3 = str.strip()
print(str_new3)
```

#### count("it")

返回子串出现的次数

```python
print(str.count("it"))

strssc = "itheima itcast boxuegu";
num = strssc.count("it")
print(f"字符串{strssc}中有{num}个it字符")

strssc_new1 = strssc.replace(" ","|")
print(f"字符串{strssc},被替换空格后，结果：{strssc_new1}")
strssc_new2 = strssc_new1.split("|")
print(f"字符串{strssc},按照|分隔后，得到：{strssc_new2}")
```

## 第二章 运算符

### 算数运算符

```python
print("加法",1+3)
print("减法",9-3)
print("乘法",5*3)
print("除法",9/4)
print("取余",9%4)

print("整除法",9//4) # 保留整数，舍弃小数部分
print("幂运算",2**3)

2*(3**2) # 18
print(2**3**2) # 从右向左 512
print(9**0.5) # 3
27**(1/3) #3
print(2**-3) # 2的-1/3次

a = int(input("请输入二次项系数"))
b = int(input("请输入一次项系数"))
c = int(input("请输入常数项"))
num = (b*b)-(4*a*c);
sum1 = (-b+(num**0.5))/(2*a);
sum2 = (-b-(num**0.5))/(2*a);

print("方程的根是{:.2f}和{:.2f}".format(sum1,sum2))
```

### 赋值运算符

+=、-=、*=、/=、//=、%=、**=、<<=、>>=、&=、^=、|=

- abs(x):x的绝对值
- round(x,位数):保留小数位数。四舍五入
- ceil(x):向上取整。 5.34 结果6
- floor(x)：向下取整

#### 引入库

```python
from math import *
print(sin(67))

import math
print(math.ceil(9.3))
```



### 关系运算符

```python
print("9d大于7吗",9>7)
x = 3
print(0<x<9)
print("python"=="Python")
print("abc">"abr")
```



### 逻辑运算符

- not 非
- and 与
- or 或

这是一个判断二次方程ax^2+bx+c=0是否有实数根的条件。如果a不等于0且b^2-4ac大于等于0，则有实数根。

```
a=4 b=4 c=2
```

### 位运算符

**不考**

位运算符是在二进制或二进制数的基础上进行的运算。

- &（按位与）
  - 如果同一位置的两个二进位都为1，则该位置的结果为1，否则为0。
- |（按位或）
  - 如果同一位置的两个二进位都为0，则该位置的结果为0，否则为1。
- ^（按位异或）
  - 如果同一位置的两个二进位相异，则该位置的结果为1，否则为0。
- ~（按位取反）
  - 对二进制数的每一位取反，即把1变为0，把0变为1。
- <<（左移）
  - 将二进制数的所有位全部左移若干位，由"<<"右边的数指定移动的位数，高位丢弃，低位补0。
- （右移）
  - 将二进制数的所有位全部右移若干位，由">>"右边的数指定移动的位数，高位补0，低位丢弃。
- &（按位与）
  - 如果同一位置的两个二进位都为1，则该位置的结果为1，否则为0。
- |（按位或）
  - 如果同一位置的两个二进位都为0，则该位置的结果为0，否则为1。
- ^（按位异或）
  - 如果同一位置的两个二进位相异，则该位置的结果为1，否则为0。
- ~（按位取反）
  - 对二进制数的每一位取反，即把1变为0，把0变为1。
- <<（左移）
  - 将二进制数的所有位全部左移若干位，由"<<"右边的数指定移动的位数，高位丢弃，低位补0。
- （右移）
  - 将二进制数的所有位全部右移若干位，由">>"右边的数指定移动的位数，高位补0，低位丢弃。

## 第三章 逻辑控制

### 循环语句

```python
for 循环变量 in 目标对象:
    循环体
    
```

从目标对象中逐一提取元素，放在循环变量中，对于提取的每个元素执行一次循环。

#### 目标对象

##### 字符串

```python
for i in "i like you":
     print(i,end="")
# 循环变量i 用于保存每次循环访问的目标对象的元素。
```

##### range(初值，终值，步长)

- 功能:返回一个整数序列。
- 参数:从初值开始，每次增加一个步长，取值到终值为止，不包含终值。
- 不写初值，默认从0开始
- 步长不写：默认是1，为正：从左到右。 为负：从右往前

```python
for i in range(1,10,1):
    print(f"{i}",end=" ")
print()
# 0-9
for i in range(10):
    print(f"{i}",end=" ")
print()
# 输出偶数
for i in range(2,11,2):
    print(f"{i}",end=" ")
print()
# 从大到小
for i in range(10,1,-1):
    print(f"{i}",end=" ")
print()
```



```python
x = int(input("请输入一个数:"))
for i in range(2,x,1):
    if x%i==0:
        print(f"{x}不是素数")
        break
    # if i==x-1:
    #     print(f"{x}是素数")
#不是素数
else:
    print(f"{x}是素数")
# for 循环变量 in 对象:
#       语句1
# else:
#       语句2
```

当语句1中的break执行时，则语句2不被执行。break没有执行，语句2才被执行.

else是循环正常结束时执行的代码，break跳出循环，不会执行else。



 例1:输入一个字符串python。当遇到字符h，结束输出pyt

```python
for i in "python":
    if(i=="h"):
        break
    print(i,end="")
print("结束")
```

例2:输入一个字符串python。当遇到字符h，跳过输出pyton

```python
for i in "python":
    if(i=="h"):
        continue
    print(i,end="")
```

continue:结束本次循环，跳过循环体后面的语句继续执行下一次循环

### 分支语句

#### 单分支结构

```python
if 条件:
    语句
```

练习1:  98分，判断成绩等级，不低于60分及格。

```python
import math

score=45
if score>=60:
    print("合格")
print("程序正常结束")

weight = float(input("请输入重量:"))
total = 12
if weight>5:
    total =total+math.ceil(weight-5)*2;
    print(f"{weight},费用是{total}")
else:
    total = 12
    print(f"{weight},费用是{total}")

score = float(input("请输入成绩:"))
str=""
if score>=90:
    str = "优秀"
elif score>=80 and score<=89:
    str = "良好"
elif score >= 60 and score <= 79:
    str = "及格"
else:
    str = "不及格"
print(f"{score}的成绩等级为{str}")
```



```python
price = float(input("请输入消费金额:"))
flag = input("如果是会员输入y，如果否输入n:")
# 购物金额范围
if price>=5000:
    cost=price*0.7
elif price>=2000:
    cost=price*0.8
elif price>=1000:
    cost=price*0.9
else:
    cost=price
#判断是否为会员
if flag=="y":
    cost=cost*0.95
    if price>3000:
        cost=cost-50
print(f"实际花费了{cost},优惠了{price-cost}")
#循环退出
vip = input("请输入是否退出程序y/n:")
i=i+1
```

### 循环语句

使用while循环，不确定次数循环

```python
while 条件:
	循环体

```



```python
for 循环变量 in 目标对象:
    循环体
```



## 第四章 综合数据类型

组合数据类型：

- 序列类型：数列。按一定的顺序排序成的一组数。
  - 字符串，列表：利用内存中一段连续的空间存储列表。支持双向索引。不可变的**。 **不能修改，增加
  - 列表：支持增删改查。可变的。
  - 字符串
- 集合类型
- 映射类型

### 列表

列表是可变的，可以添加，删除和修改元素

频繁修改场景

#### 创建列表

```python
list = [1,3,5,"rr"]
print(list)
```

#### 函数list()

```python 
list2 = list()#空列表
print(list2,len(list2))
list3 = []#空列表
```

#### 数据转换为列表

```python
range(1,20,2)#生成整数序列
list5 = list(range(1,20,2))
print(list5)
```

#### 字符串生成列表

```python
list6 = list("hello")
print(list6)
```

#### 函数返回列表

```python
x = "i am a student"
list7 = x.split(" ")
print(list7)
```

#### 列表推导式

3-30能被3整除的整数作为列表的序列

```python
list4 = []
for i in range(3,31):
    if i%3==0:
        list4.append(i)
print(list4)

list5 = [i for i in range(3,31) if i%3==0]
print(list5)
[列表的项 for 循环变量 in range(初值,终值,步长) if 条件]
```

#### 列表的增删改查

##### 列表增加元素

列表.append(元素)

```python
x = ["apple","pear","banana"]
x.append("tomato")
print(x)
```

列表.insert(索引，值)

```python
x.insert(2,"peach")
print(x)
```

##### 列表元素的删除

2.1 列表.remove(值)

```python
x.remove("pear")
print(x)
```

2.2 列表.pop(索引):删除指定索引的元素；默认删除最后一个元素。返回删除的元素值，然后删除

```python
y = x.pop()  #默认删除最后一个元素
print(y,x)
y=x.pop(0)   #删除索引为0的元素
print(y,x)
```

##### 修改元素

```python
x = ["apple","pear","banana"]
x[0] = "sss"
print(x)
```

#### 列表的运算

##### 切片

在Python中，切片是一种获取序列中特定部分的方法。切片可以用于列表、元组、字符串等序列类型。
切片的基本语法是

```python 
序列[起始:结束]
```

其中，起始和结束都是可选的，如果不指定起始，则默认从序列的开始位置开始。如果不指定结束，则默认到序列的结束位置结束。
切片可以用于获取序列的一部分，也可以用于修改序列的一部分。
例如，对于一个列表[1,2,3,4,5,6,7,8,9]，可以使用切片[1:5]来获取列表的一部分，得到[2,3,4,5]。
此外，切片还可以用于修改序列的一部分。例如，可以使用切片[1:5] = [10,20,30,40]来修改列表的一部分，得到[1,10,20,30,40,6,7,8,9]。

##### s+t3

```python 
print([1,2,4]+["he","ee"])
```

##### 元素是否在列表中

```python 
x=[1,3,5,7,8]
print(2 in x)

```

##### 序列s复制n次

```python 
# 4. s*n :将序列s复制n次
print([1,3,4]*3)
```

#### 列表的复制

生成一个新的列表

```python
ylist = xlist.copy()
```

指向列表，没有生成新的列表

```python 
zlist = xlist.zlist
```

对xlist列表操作就是对zlist的操作

```python
# 定义一个列表xlist，包含元素1，3，5，6
xlist=[1,3,5,6]
# 创建一个ylist列表，复制xlist的所有元素
ylist=xlist.copy()
# 打印xlist和ylist的内容
print(xlist,ylist)

# 定义一个zlist，引用xlist的所有元素
zlist=xlist
# 修改xlist的第一个元素为111
xlist[0]=111
# 打印zlist和xlist的内容
print(zlist,xlist)
```

#### 列表的排序

##### 升序排序

```python
列表.sort()#默认是升序排序
列表.sort(reverse=Ture)#降序排序
sorted(x) #接受任何可迭代的数据,返回一个新的列表。默认是升序
sorted(x,reverse=True) #降序排序
y=sorted(x,reverse=True)
print(y)
```

#### 列表的数据操作

- 最大值max()
- 最小值min()
- 总和sum()
- 长度len()

#### 列表的操作

##### 列表的索引

```python
x=[1,3,5,7,8,5,5]
x.index(5) # 返回元素的第一次出现的索引值
x.count(5) # 返回元素出现的次数
```

##### 列表添加元素

```python
scores = []
for i in range(10):
    grade = float(input("请输入成绩:"))
    scores.append(grade)
print(scores)
```

##### 删除最高分

```python
scores.sort()
maxg = scores.pop() # 返回删除的元素。并删除。
```

##### 删除最低分

```python
ming = scores.pop(0)
print(f"最高分:{maxg},最低分{ming}")
```

##### 计算平均分

```python
avg = sum(scores)/len(scores)
print(f"平均分{avg:.2f}")
```

#### 二维列表

```python
score=[
       ["101","Mary",80,85,90],
       ["102","rose",80,90,95],
       ["103","Mike",75,72,65],
       ["104","hary",90,93,88]
       ]

for i in range(len(score)):
    grade = score[i][2:];
    score[i].append(grade)
print(score)

# 排序
score.sort(key=lambda x:x[-1],reverse=True)
print(score)

```

### 元组

不可改变数据类型，无法添加元素

#### 创建

```python
tuple2=() #创建空元组
tuple3=("python")  # <class 'str'>
tuple4=("python",) # 单个元素元祖，加个,
print(type(tuple3),type(tuple4))
typle25=(1,2,4,6,8,5.7,"hello") # 元祖的类型可以多种的。
print(typle25)
```

#### 转换为元组类型

```python
tuple()
tuple6=tuple("python")
print(tuple6)
# 将列表转换成元祖
tuple7=tuple([1,3,4,6,76])
print(tuple7)
```

#### 元组的操作

##### 索引

```python
元组[i]
```

##### 切片

**重点**

```python
x=(1,2,4,6,8,9)
print(x[2:4])
```

##### 连接

```python
元组1 + 元组2
```

##### 复制

将元组复制i次

```python
元组 * i 
i * 元组
```

##### 求长度

```python
len(元组)
```

##### 对元组元组循环

```python

```

##### 查找元组中元素

返回值为布尔类型

##### 删除元组

##### 返回最大值

##### 返回最小值

### 字典

字典：通过任意键找到一组值的信息的过程叫映射。

字典的键重复，后面的键值会替换前面的键值对

特点：无序，可变数据类型

- 无序：元素没有固定的顺序。不能用索引和切片。
- 可变数据类型：支持增删改。
- 键值对： key:value,键不能重复，是唯一的。不可变数据类型：整数，浮点，字符串，元祖。

#### 字典的操作

##### 创建字典

```python
dict2={"学号":1001,"姓名":"张三","地址":"大连"}
print(dict2)
```

##### 空字典

```python
dict3={}
dict4=dict()
print(dict3,dict4)
dict2={"学号":1001,"姓名":"张三","地址":"大连","学号":1002}
print(dict2)
```

##### 字典的增删改查

###### 添加键值对

```python
dict2["年龄"]=20
print(dict2)
```

###### 添加字典元素

```python
dict2.update({"电话":"12343","性别":"女"})
print(dict2)
```

###### 删除字典元素

```python
del 字典名[key] # 删除给定键的键值对。
dict2.pop("年龄")
print(dict2)
del dict2["性别"]
print(dict2)
```

###### 修改字典元素

```python
dict2["地址"]="北京"
print(dict2)
```

#### 遍历字典

##### 遍历键

```python
print(dict2.keys())  # 以列表返回一个字典的所有键。['学号','姓名','地址','电话']
for i in dict2.keys():
    print(i,end=" ")
for i in dict2: # dict2 默认是 dict2.keys(
    print(i,end=" ")
print("\n*****************")
```

##### 遍历值

```python
print(dict2.values())  # 以列表形式返回字典中的所有值。[1002,'张三','北京','12343']
for i in dict2.values():
    print(i,end=" ")
print("\n*****************")
```

##### 遍历键值对

```python
print(dict2.items())  # 返回可遍历的元祖列表。[('学号', 1002), ('姓名', '张三'), ('地址', '北京'), ('电话', '12343')]
for key,value in dict2.items():
    print(f"{key}:{value}")
```

##### 其他操作

- dict.keys()：返回包含字典所有key的列表
- dict.values()：返回包含字典所有value的列表
- dict.items()：返回包含所有（键，值）项的列表
- dict.clear()：删除字典中的所有项或元素，无返回值
- dict.copy()：返回字典浅复制脚本
- dict.get(key,default = None)：返回字典中key对象的值，若key不存在，则返回default的值（default默认值为None）
- dict.pop(key,[ ,default])：若字典中存在key，则删除并返回key对应的value；如果key不存在，且没有给出default的值，则引发KeyError异常
- dict.setdefault(key,default = None)：若字典中不存在key，则由dict[kry] - default 为赋值
- dict.update(adict)：将字典adict中键值对添加到dict中

### 集合

- 唯一性
  - 任何两个元素都不相同，每个元素只能出现一次，不重复
- 无序性
  - 一个集合，每个元素的地位都是相同的。
  - 元素之间是无序的，没有索引和位置，不能用切片
- 可变数据类型
  - 支持增删改
  - 集合的元素是不可变的数据类型
    - 整数
    - 浮点
    - 字符串
    - 元组

#### 集合的操作

集合不能用切片

##### 创建集合

集合是无序的，所以输出和定义时的位置不一样

```python
set2 = {"hello",33,"hh"}
print(set2)
```

##### 空集合

```python
set4 = {}  # 空字典，不是集合
set5 = set()  # 空字典
print(type(set4),type(set5))
```

##### 增加

添加一个元素

```python
x = {"apple","pear","orange"}
x.add("melon")
print(x)
```

一次向集合中添加多个元素

```python
集合.update() # 向集合中添加多个元素，接受列表，元祖，等可迭代的数据类型
x.update(["water","frr"])
print(x)
```

##### 删除

```python
集合.discard(元素)#删除元祖，没有元素不报错。
x.discard("water3")
```

##### 修改

首先查找后删除，然后添加

```python
x.remove("water")
x.add("water2")
```

#### 集合的转换

##### 字符串转换

```python
set6 = set("pythonnnnn") #将字符串转换成集合，自动去重。
print(set6)
```

##### 元组，列表转换

```python
set7 = set((1,2,3,4,4,4))  # 去重
print(set7)
```

##### 集合转换为元组或列表

```python
tuple2 = tuple(set7)
print(tuple2)
```



## 第五章 函数

### 函数定义调用

定义函数

```python
def 函数名(参数):
    函数体
    return 返回值
```

练习：定义逆序函数

```python
def rev(num):
   """
   这个函数用于将输入的数字转换为字符串，然后利用切片的方式进行逆序，最后再将结果转换为整数返回。
   参数:
   num: 需要进行逆序的数字
   返回值:
   y: 逆序后的数字
   """
   # 将输入的数字转换为字符串
   y = str(num)
   # 利用切片的方式进行逆序
   y = y[::-1]
   # 将逆序后的字符串再转换为整数
   y = int(y)
   return y
```

引用模块

```python
from functons.funs import *
```

调用函数

```python
num = int(input("请输入一个整数"))
res = rev(num)
print(f"{num}的逆序数是{res}")
```

练习：显示1000以内的回文数。每行显示10个。

```python
n = 0
for i in range(1001):
    if i == rev(i):
        print(f"{i:5d}",end=" ")
        n = n+1
        if n%10 == 0:
            print()
```

### 函数模块化

将函数放到python文件中，称为函数模块文件

路径：相对路径

```python
import sys
sys.path.append(r"..//")
from 文件夹.py文件 import *

if __name__=='__main__':
# 判断是否为主程序。如果运行当前文件，则执行；若当作模块被引用，则不执行。
```

### 参数传递

#### 位置传参

```python
def happy(name,age):
    print(name+"生日快乐")
    print(age,"生日快乐")

# 调用函数
happy("张三",20) #顺序和个数必须和形参一致。
```

#### 关键值传参

```python
# 调用参数
happy(name="赵丽",age=18) # 顺序可以不一样，但是参数名和形参一样。
happy("赵丽",age=18) #前面是位置传参，后面是关键字传参。
#happy(name="张思",20) #位置传参在前，关键字在后。
```

#### 默认传参

定义函数时叫默认参数。

调用函数：关键字传参

```python
def happy2(name="张三",age=20):
    print(name+"生日快乐")
    print(age,"生日快乐")

# 调用
happy2() # 不传参数，使用默认值
happy2("美美") # 位置传参，从前往后对应
happy2(age=20) #关键字传参，name使用默认值


print("*"*20)
```

#### 可变数量参数

```python
def fun(*para):
    print(type(para))
    for item in para:
        print(item)

# 调用
fun(10,20,30)
# 列表传递
fun([10,20,30]) #实际上成传递一个参数
# 调用时，参数前一个星花，将列表解包。
fun(*[10,20,30])  # 将列表解包。10，20，30

# 个数可变的关键字参数。
def fun2(**kwargs):
    print(type(kwargs))
    for key,value in kwargs.items():
        print(key,'---',value)
# 调用函数
fun2(name="张三",age=10,height=130)

dict2={'name':"zhang",'age':30}
#fun2(dict2) #错误传参
fun2(**dict2) # 调用时，字典前加两个*，解包后传递
```

### 函数返回值

return语句返回多个值

```python
return 语句返回多个值
def 函数(参数):
  函数体
  return 返回值1，return 返回值2...
```

返回多个值以元组类型保存

练习：计算一组的奇数和，偶数和

输入一个整数，输出：1~整数 的奇数和，偶数和 ,总合

```python

def getsum(num):
   """
   这个函数用于计算从1到给定数字的所有偶数和奇数的和，以及它们的总和。

   参数:
   num: 一个整数，表示要计算的范围的上限。

   返回值:
   一个元组，包含三个元素：
   s1: 从1到给定数字的所有偶数的和
   s2: 从1到给定数字的所有奇数的和
   s: s1和s2的和
   """
   # 初始化三个和为0的变量
   s = 0
   s1 = 0
   s2 = 0
   # 遍历从1到给定数字的所有整数
   for i in range(1,num+1):
       # 如果整数是偶数，加到s1上
       if(i%2==0):
           s1 += i
       # 如果整数是奇数，加到s2上
       if(i%2!=0):
           s2 += i
       # 更新总和
       s = s1+s2;
   # 返回三个和
   return (s1,s2,s)

# 调用函数，并打印结果和结果的类型
result = getsum(10)
print(result,type(result))

# 解包赋值:一个数据结构的元素解开并赋值给变量的操作
a,b,c=getsum(20)
# 列表解包
a,b,c=[10,20,40]
# 字典解包：解包键
a,b,c={'a':1,'b':2,'c':3}.keys()
print(a)
print(b)
print(c)
# 解包值
a,b,c={'a':1,'b':2,'c':3}.values()
# 解包键值对象
a,b,c={'a':1,'b':2,'c':3}.items()
print(a)
print(b)
print(c)
# 变量=元素数
```

### 变量的作用域

#### 局部变量

函数定义的形参和函数内部定义的变量

作用域：函数内部，函数结束，局部变量的生命周期结束

#### 全局变量

函数外定义的变量，活着用global关键字修饰的变量

作用域：整个程序，程序结束，全局变量的生命周期也结束

```python
c=100
def cal(a,b):
    global c
    c=200
    s=a+b+c
    return s
result=cal(2,4)
print(200)
print(result)
```

### 递归函数

练习

```python
1！=1 2！=1！*2 3！=2！*3 4！=3！*4 ... N!=(N-1)!*N
def fact(n):
    if n == 1:
        return 1
    return fact(n-1)*n

# 调用
result = fact(4)
print(result)
```

### 匿名函数

适用于，返回表达式的函数

```python
# 定义一个lambda函数s，接受两个参数a和b，返回它们的和
s = lambda a,b:a+b  # s 是 function 类型，a,b是参数，a+b是返回值。
# 打印s的类型和s(10,20)的结果，用于验证lambda函数s的正确性
print(type(s),s(10,20))
# 相当于普通函数：
def s(a,b):
    return a+b
print(s(10,30))
```

排序

```python
scores = [
    {'name':'张三','score':100},
    {'name':'李四','score':90},
    {'name':'王五','score':80},
    {'name':'赵六','score':70},
    {'name':'孙七','score':60},
]
```

对成绩进行降序排序

列表.sort() 列表对象的排序 ， 列表改变  sorted(可迭代的类型):内置函数 ，返回新对象。scores列表对象会把列表的每个字典元素传递给x，返回的是每个字典的成绩值。成绩值作为排序的key。scores.sort(key=lambda x:x['score'])  x.get('score') : 获取字典score的值。

```python
scores.sort(key=lambda x:x['score'],reverse=True)
print(scores)
```

## 第六章 文件操作

### 文件的创建

用于打开文件，返回一个文件对象

无法打开文件，返回OSError异常，通用异常，表示操作系统相关的错误

```python
open(file,mode='r',encoding=None)
```

第一个参数file是必须的，它指定了要打开的文件的名称

```python 
"D:\\file"
```

第二个参数mode是可选的，他指定了打开文件的模式

- r 读取 默认
- w 写入 创建或覆盖文件内容
- a 追加 追加文件末尾，不存在则创建文件

第三个参数是可选的，它指定了文件的编码格式

练习：读取file.txt内容

创建文件对象

```python
file_r=open("file.txt",'r')
str2 = file_r.read()
print(str2)
file_r.close()
```



相对路径

```python
file_r3=open("../outfile.txt","r")
print(file_r3.read())
```



### 关闭文件

打开的文件占用系统资源

若程序因异常关闭，产生数据丢失

```python
文件对象.close()
```

自动关闭文件

```python
with open("file.txt", "r") as file_r4:
    file_r4.read()
```



文件操作的三步

- 创建文件
- 读和写
- 关闭文件

### 读操作

#### 直接读整个文件

```python
文件读取.read(字符数)
```

练习：输出古诗.txt内容

```python
# 打开名为"古诗.txt"的文件，以只读模式打开，并将文件对象赋值给file_r5
file_r5=open("古诗.txt","r")
# 使用with语句打开文件，可以自动关闭文件，减少忘记关闭文件的可能性
with open("古诗.txt","r") as file3:
   # 读取文件内容，并将内容赋值给str2
   str2 = file3.read()
   # 输出str2的内容，此时文件还未关闭
   print(str2)  #先输出，在关闭文件
# 文件已经关闭，再次输出str2的内容
print(str2) #先关闭文件，在输出
```

#### 一次读一整行

```python 
文件对象.readline()
```

```python
# 打开名为"古诗.txt"的文件，以只读模式打开
file4 = open("古诗.txt","r")
# 读取文件的第一行内容
str2=file4.readline()
# 读取文件的第二行内容
str3=file4.readline()
# 打印第一行内容
print(str2)
# 打印第二行内容
print(str3)
```

#### 使用循环读文件

```python
# 打开名为"古诗.txt"的文件，以只读模式打开
file4=open("古诗.txt","r")
# 遍历文件中的每一行
for line in file4: # line 文件对象的每一行内容。默认调用readline()。
   # 打印每一行的内容
   print(line)
# 关闭文件
file4.close()
```

#### 一次性读所有行

```python
文件对象.readlines()
```

```python 
# 打开名为"古诗.txt"的文件，以只读模式打开
file4=open("古诗.txt","r")
# 使用rawlines()方法读取文件中的所有行，并将其存储在list2中
list2=file4.rawlines()
# 打印list2的内容和其类型
print(list2,type(list2))
```

### 目录及写入文件操作

创建目录

os模块：是系统的内置模块，提供了对文件，目录的接口函数

- mkdir()：创建文件目录
- rkdir()：删除文件目录
- path.exists()：判断文件或文件夹是否存在

练习：在ts文件夹下根据每个诗人创建一个文件夹，打印诗人名，不考虑重复

```python
# 打开名为"古诗.txt"的文件，以只读模式打开
file=open("古诗.txt","r")
# 遍历file 进行读
for line in file:
   # 判断是否是标题行，标题行的前3个字符是数字
   if line[:3].isdigit():
       # 获取诗人名，诗人名在"："后面
       index = line.find("：")
       name=line[3:index]
       # 创建诗人名的文件夹，文件夹路径为"ts\\"+name
       lj="ts\\"+name
       # 判断这个文件夹是否存在,如果不存在就创建
       if not os.path.exists(lj):
           os.mkdir(lj)
# 关闭文件
file.close()
```



## 第七章 类与对象

**少考**

类是和对象的关系：

类是对象的抽象，对象是类的实例

```python
pass #空语句
```







## 第八章 第三方库

**不考**





## 练习

```python
2*(3**2) # 18
print(2**3**2) # 从右向左 512
print(9**0.5) # 3
27**(1/3) #3
print(2**-3) # 2的-1/3次
```

### 求三角形面积

```python
a = int(input("请输入边长1"))
b = int(input("请输入边长2"))
c = int(input("请输入夹角"))
S = ceil((a*b*sin(c))/2)
print(f"三角形面积是{S:.2f}")
```

### 计算1-100的和

```python
sum=0
for i in range(1,101):
  sum=sum+i
print(sum)
```

### 计算1-100的和偶数和

```python
sum=0
for i in range(2,101,2):
  sum=sum+i
print(sum)
```

### 计算车费

某地出租车计费程序，规则如下：
白天起步:2公里内8元。2公里以上续程单价每公里为2.0元。夜间(22:00-次日5:30):如下白天起步：2公里内8元，2公里以上续程单价每公里2.0元夜间(22:00-次日5:30):2公里内10元，2公里以上续程单价每公里2.4元此外在12公里/小时(含12公里/每小时)以下，累计每满2分钟计费1元

```python
time = input("请输入时间(4:30):")
h = int(time[:time.find(":")]) # 截取的是小时 find
s = int(time[time.find(":")+1:]) # 截取的是分钟

time2 = int(input("请输入低速行驶的时间分钟："))
dis = float(input("请输入公里数："))

# 白天
if 6<=h<=22 or (h==5 and s>30):
    a1=2
    b1=8
else:
    a1=2.4
    b1=10

if dis <=2:
    cost = b1
else:
    cost = b1 +(dis - 2) *a1
cost=cost+time2/2
print(f"打车时间{time},行驶的公里数{dis},低速的时间{time2},花费{cost:.2f}元")
```

### 计算一年中的第几天

这段代码的功能是计算输入的日期是一年中的第几天。
首先，通过input()函数获取用户输入的年份、月份和天数。然后，定义一个元组months，其中存储了每个月的天数。
接着，判断输入的月份是否在1-12之间。如果在，则将对应的月份天数加到sum中。
然后，将输入的天数加到sum中。
接下来，判断输入的年份是否是闰年。如果是，则将sum加1，因为闰年的2月有29天。
最后，打印出sum，表示输入的日期是一年中的第几天。
这段代码的主要目的是通过计算，得到输入日期在一年中的位置。

```python
# 1、获取用户输入的年份、月份和天数
year = int(input('请输入年份:\n'))
month = int(input('请输入月份:\n'))
day = int(input('请输入天数:\n'))

# 2、定义一个元组months，其中存储了每个月的天数
months = (0,31,59,90,120,151,181,212,243,273,304,334)

# 3、判断输入的月份是否在1-12之间，如果在，则将对应的月份天数加到sum中
if 0 < month <= 12:
  sum = months[month - 1]
sum += day

# 4、判断输入的年份是否是闰年，如果是，则将sum加1，因为闰年的2月有29天
leap = 0
if (year % 400 == 0) or ((year % 4 == 0) and (year % 100 != 0)):
  leap = 1
  # ts=(31,29,31,30,31,30,31,31,30,31,30,31)
if (leap == 1) and (month > 2):
  sum += 1

# 5、打印出sum，表示输入的日期是一年中的第几天
print (f'是第{sum}天')
```

```python
# 1、获取用户输入的年份、月份和天数
year = input('请输入年份:\n')
month = input('请输入月份:\n')
day = input('请输入天数:\n')

# 2、根据年份是否是闰年，定义一个元组ts，其中存储了每个月的天数
if (year % 400 == 0) or ((year % 4 == 0) and (year % 100 != 0)):
   ts=(31,29,31,30,31,30,31,31,30,31,30,31)
else:
   ts=(31,28,31,30,31,30,31,31,30,31,30,31)

# 3、使用切片和sum()函数，计算输入的日期是一年中的第几天
k = sum(ts[:month-1])+day  # 切片

# 4、打印出k，表示输入的日期是一年中的第几天
print(k)
```

### 集合的操作练习

从键盘输入n，然后输入n个列表输出：包含重复元素的列表个数。输出：2个有重复元素的列表。

```python
# 定义一个函数，用于统计输入列表中有多少个重复元素
def count_duplicates():
   """
   功能描述：统计输入列表中有多少个重复元素
   参数：无
   返回值：重复元素的个数
   """
   n=int(input("请输入列表的个数"))  # 4
   count=0
   # 循环n次，每次让用户输入一个列表
   for i in range(n): # 0,1,2,3
       list2 = eval(input("请输入列表："))
       set2=set(list2)
       # 如果集合的长度不等于列表的长度，说明列表中有重复元素
       if len(set2)!=len(list2): # 集合去重后的长度 不能 列表的长度，有重复
           count=count+1
   # 打印出重复元素的个数
   print(f"重复列表的个数{count}")

count_duplicates()
```

### 学生管理系统

```python
# encoding=utf-8
# 创建一个学生信息列表
persons=[{"学号":"101","姓名":"张三1","电话":"15833"},
        {"学号":"102","姓名":"张三2","电话":"158333"},
        {"学号":"103","姓名":"张三3","电话":"1583333"}]
# 增加菜单
print("******************")
print("1. 添加学生信息")
print("2. 查找学生信息")
print("3. 删除学生信息")
print("4. 修改学生信息")
print("5. 退出")
print("******************")
choice=int(input("请输入你的选择(1-5):"))
while True:
   if choice==1:
       # 1. 添加学生信息
       # 创建空字典
       per={}
       sno=input("请输入学号:")
       sname=input("请输入姓名:")
       tel=input("请输入电话:")
       # 像字典中添加元素
       per["学号"]=sno
       per["姓名"]=sname
       per["电话"]=tel
       # 把这个字典的学生添加到通讯录中 列表persons中
       persons.append(per)
       print("保存成功")
   elif choice==2:
       # 显示通讯录
       if (len(persons) != 0):  # 通讯录不为空
           sno = input("请输入要查找的学生学号:")
           # 首先遍历列表persons
           for p in persons:  # p是字典
               # 判断sno是否在这个p中
               if sno in p.values():
                   for p in persons:  # P 的元素类型是字典
                       for key, value in p.items():
                           print(f"{key}:{value}")
                   print("查找成功")
                   break  # 执行break,for--else 后的else不执行
           else:  # break 没有执行，才执行else
               print("没有找到该学生")
       else:
           print("通讯录为空")
   elif choice==3:
       # 2. 删除学生信息
       if(len(persons)!=0): # 通讯录不为空
               sno=input("请输入要删除的学生学号:")
               # 首先遍历列表persons
               for p in persons: # p是字典
                   # 判断sno是否在这个p中
                   if sno in p.values():
                       # 删除字典p
                       persons.remove(p)
                       print("删除成功")
                       break  # 执行break,for--else 后的else不执行
               else:   # break 没有执行，才执行else
                   print("没有找到该学生")
       else:
           print("通讯录为空")
   elif choice==4:
       # 3. 修改学生信息
       if(len(persons)!=0): # 通讯录不为空
               sno=input("请输入要修改的学生学号:")
               # 首先遍历列表persons
               for p in persons: # p是字典
                   # 判断sno是否在这个p中
                   if sno in p.values():
                       # 修改字典p
                       p["姓名"]=input("请输入修改后的姓名:")
                       p["电话"]=input("请输入修改后的电话:")
                       print("修改成功")
                       break  # 执行break,for--else 后的else不执行
               else:   # break 没有执行，才执行else
                   print("没有找到该学生")
       else:
           print("通讯录为空")
   else:
       break
   # 用户是否继续输入
   choice = int(input("请输入选项(1-5):"))
```

### 学生管理系统-列表

```python
# 定义学生学号和姓名的列表
snos = ["1001","1002","1003","1004"]
snames = ["张三","李四","王五","赵六"]

# 1.显示所有学生的信息
for i in range(len(snos)):  #0,1,2,3
   # 使用print函数打印学号和姓名
   print(snos[i],snames[i])
   # 使用f-string格式化字符串，打印学号和姓名
   print(f"{snos[i]}:{snames[i]}")

# 2.查询：输入学号，查询姓名
stu = input("请输入学号：")
# 判断学号不存在
if stu not in snos:
   print("学号不存在")
else:
   # 学号的索引
   k = snos.index(stu) # 返回元素第一次出现的索引
   # 输出学号对应的姓名。索引一样的索引一样
   print(snames[k])

```

### 学生管理系统

```python
# 初始化一个空的学生列表
students = []
while True:
   # 显示操作菜单
   print("\n学生管理系统：")
   print("1. 显示所有学生信息")
   print("2. 添加学生信息")
   print("3. 删除学生信息")
   print("4. 查询学生信息")
   print("5. 退出系统")
   choice = int(input("请选择操作编号："))
   # 操作逻辑
   if choice == 1:
       # 显示所有学生信息
       if not students:
           print("当前暂无学生信息。")
       else:
           for idx, student in enumerate(students):
               print(f"{idx + 1}. 学号: {student['sno']}, 姓名: {student['name']}")
   elif choice == 2:
       # 添加学生信息
       sno = input("请输入要添加的学生学号：")
       name = input("请输入学生姓名：")
       students.append({"sno": sno, "name": name})
       print(f"成功添加学生信息：学号 - {sno}，姓名 - {name}")
   elif choice == 3:
       # 删除学生信息
       sno_to_delete = input("请输入要删除的学生学号：")
       for student in students.copy():
           if student["sno"] == sno_to_delete:
               students.remove(student)
               print(f"成功删除学生信息：学号 - {sno_to_delete}")
               break
       else:
           print("未找到该学生信息。")
   elif choice == 4:
       # 查询学生信息
       sno_to_query = input("请输入要查询的学生学号：")
       for student in students:
           if student["sno"] == sno_to_query:
               print(f"学号: {student['sno']}, 姓名: {student['name']}")
               break
       else:
           print("未找到该学生信息。")
   elif choice == 5:
       # 退出系统
       print("正在退出系统...")
       break
   else:
       print("无效的选择，请重新输入。")
```

### 斐波那切数列

1,1,2,3,5,8,13,21,34,55

1 2 3 4 5 6 7 8 9 10

fac(n)=fac(n-1)+fac(n-2)

```python
def fanbo(n):
   """
   这是一个递归函数，用于计算斐波那契数列的第n项。

   参数:
   n: 要计算的斐波那契数列的项数，是一个大于等于1的整数。

   返回值:
   返回斐波那契数列的第n项。

   异常描述:
   如果n不是一个大于等于1的整数，函数可能会抛出异常。
   """
   # 如果n等于1或2，则返回1，因为斐波那契数列的前两项都是1
   if n == 1 or n == 2:
       return 1
   # 否则，返回斐波那契数列的第n-1项和第n-2项之和
   return fanbo(n-1)+fanbo(n-2)  #n变化:递减

# 调用
print(fanbo(7))
# 前12项值的和
sum = 0
for i in range(1,13):
   # 累加斐波那契数列的前12项
   sum+=fanbo(i)
print(sum)
```

### 汉塔塔

经过三步

第一步：将(n-1)个盘子  A----->B

第二步：将 最后 的盘子  A----->C

第三步：将(n-1)个盘子  B----->C

```python
# 定义一个全局变量count，用于记录汉诺塔问题的步数
count = 0


def han(n,a,b,c):
   """
   汉诺塔问题的递归解法

   参数:
   n: 盘子的数量
   a: 起始柱
   b: 辅助柱
   c: 终止柱

   返回值:
   无返回值，但会更新全局变量count，记录移动步数
   """
   # 当只有一个盘子时，直接将盘子从a柱移到c柱，并将步数加一
   if n==1:
       print(a,'--->',c)
       global count
       count += 1
   else:
       # 将n-1个盘子通过辅助柱b，从起始柱a移到辅助柱c
       han(n-1,a,c,b)
       # 将最底下的一个盘子从起始柱a移到终止柱c
       han(1,a,b,c)
       # 将n-1个盘子通过起始柱a，从辅助柱b移到终止柱c
       han(n-1,b,a,c)


# 如果当前脚本是主程序，则调用han函数，将4个盘子从A柱移到C柱
if __name__ == "__main__":
   han(4,'A','B','C')
   # 输出移动步数
   print(f"{count}步")
```

### 编写一个判断两位质数的小数

```python
def isprime(n):
   """
   判断一个数是否为质数

   参数:
   n : int
       需要判断的数

   返回:
   bool
       如果n是质数，返回True，否则返回False
   """
   # 从2开始遍历到n-1
   for i in range(2,n):
       # 如果n能被i整除，则n不是质数，返回False
       if n%i == 0:
           return False
   # 如果n不能被2到n-1的任何数整除，则n是质数，返回True
   return True


# 测试10-20之间的质数
print(isprime(55))
```

### 100内判断绝对质数

```python
def rev(num):
   """
   功能描述：将输入的数字转换为字符串，然后反转字符串，再将反转后的字符串转换为整数
   参数：
   num：需要反转的数字
   返回值：
   反转后的整数
   """
   # 将输入的数字转换为字符串
   y = str(num)
   # 反转字符串
   y = y[::-1]
   # 将反转后的字符串转换为整数
   y = int(y)
   return y
# 10-100之间的绝对质数，3个一行
count = 0
for i in range(10,100):
   # 判断i是否为质数
   if isprime(i) and isprime(rev(i)):
       print(i,end='    ') # 后面四个空格
       # 进行质数计数
       count += 1
       # 判断是否是3的倍数
       if count%3 == 0:
           print()
```

### 100内的隔阂巴德猜想

```python
# 定义变量z和items，z用于计数，items用于存储满足条件的数字
z,items=0,[]
# 循环遍历从4到99的所有奇数
for i in range(4,100,2):
   # 循环遍历从2到99的所有数字
   for x in range(2,100):
       # 循环遍历从2到99的所有数字
       for y in range(2,100):
           # 判断x和y是否为质数，并且i等于x+y，且i不在items列表中
           if isprime(x) and isprime(y) and i==x+y and i not in items:
               # 将满足条件的i添加到items列表中
               items.append(i)
               # 打印满足条件的i，以及i的两个因数x和y
               print("{:2d}={:2d}+{:2d}".format(i,x,y),end="\t")
               # 计数器z加1
               z+=1
               # 如果z是5的倍数，则换行
               if z%5==0:
                   print()
```

### 三边是否构成三角形

```python

def sjx(a,b,c):
   """
   判断三边长能否构成三角形，并返回三角形类型

   参数:
   a,b,c : 三个边长

   返回值:
   0 : 不能构成三角形
   1 : 等边三角形
   2 : 等腰三角形
   3 : 直角三角形
   4 : 一般三角形
   """
   lx=0
   # 判断三边长是否能构成三角形
   if a+b<c and a+c<b and b+c<a:
       # 判断三边长是否相等
       if a==b==c:
           lx=1
       # 判断是否为等腰或等边三角形
       elif a==b or a==c or b==c:
           lx=2
       # 判断是否为直角三角形
       elif a**2+b**2==c**2 or a**2+c**2==b**2 or b**2+c**2==a**2:
           lx=3
       else:
           lx=4
   return lx

# 输入三个边长
x=eval(input())
y=eval(input())
z=eval(input())
# 判断输入的三个边长能否构成三角形，并打印结果
m=sjx(x,y,z)
if m==0:
   print("不能构成三角形")
elif m==1:
   print("等边三角形")
elif m==2:
   print("等腰三角形")
elif m==3:
   print("直角三角形")
else:
   print("一般三角形")
```

### 计算字符串中大小写字母的数量

```python
def func(x):
  """
  计算输入字符串中大写字母和小写字母的数量

  参数:
  x: 输入的字符串

  返回值:
  返回一个元组，第一个元素是大写字母的数量，第二个元素是小写字母的数量
  """
  # 初始化大写字母和小写字母的计数器
  upper_count = 0
  lower_count = 0
  # 遍历输入字符串中的每个字符
  for a in x:
      # 如果字符是大写字母，大写字母计数器加一
      if a.isupper():
          upper_count += 1
      # 如果字符是小写字母，小写字母计数器加一
      elif a.islower():
           lower_count += 1
      # 如果字符既不是大写字母也不是小写字母，跳过此次循环
      else:
           continue
  # 返回大写字母和小写字母的数量
  return upper_count,lower_count

if __name__ == '__main__':
  # 从用户输入获取字符串，并调用func函数计算大写字母和小写字母的数量
   b = func(input("请输入字符串:"))
   # 打印结果
   print(b)
```

### 商店

```python
#encoding:utf-8
# 定义商品和价格的字典
"""
商品和价格的字典，键为商品名称，值为商品价格
"""
goods={
       '方便面':4,
       '奶茶':8,
       '洗衣粉':20,
       '矿泉水':4
}
# 购物车字典，键为商品名称，值为购买数量
Cart={}
# 显示商品：
def show():
   """
   显示所有商品及其价格
   """
   # 遍历商品字典，打印商品名称和价格
   for key,value in goods.items():
       print(f"{key}:{value}元")
   print("="*20)
# 购买商品
def buy():
   """
   购买商品，输入商品名称和购买数量，将商品和数量添加到购物车，计算总消费金额
   """
   # 初始化总消费金额为0
   count = 0
   while True:
       # 输入购买的商品名称，如果输入'end'，则退出购买
       input_in = input("请输入您要购买的东西,输入end退出购买")
       if input_in == 'end':
           print("消费总金额为{}".format(count))
           break
       # 遍历商品字典，如果输入的商品名称在字典中，则进行购买
       for key, values in goods.items():
           if key == input_in:
               # 输入购买的数量
               count_num = int(input("请输入您的购买数量"))
               # 将商品名称和数量添加到购物车
               Cart[input_in]=count_num
               # 计算总消费金额
               count += values * count_num
       # 打印购物车内容和当前消费金额
       print("您的购物车里现在有", Cart)
       print("目前消费金额为{}".format(count))
def main():
   """
   主函数，显示商品和购买商品
   """
   show()
   buy()
if __name__== '__main__':
   # 如果是主模块，则执行主函数
   main()
```

