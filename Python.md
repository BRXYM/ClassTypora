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

##### 元组



#### 集合类型

##### 集合

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

#### 创建列表：[]

```python
list = [1,3,5,"rr"]
print(list)
```

#### 创建列表：函数list()

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

##### 切片

```python
x=(1,2,4,6,8,9)
print(x[2:4])
```

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

### 参数传递顺序

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















## 第六章 文件操作

































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

