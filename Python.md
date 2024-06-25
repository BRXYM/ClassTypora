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

#### 数据类型

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

###### 布尔类型

True 1 ; 
False 0,0.0

#### 字符串

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





















### 元祖



### 字典



## 第五章 函数

### 函数定义调用

### 参数传值和返回值

### 递归函数





## 文件操作

































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



