# C++复习

## 一、概念

### 1、C++输入输出标准流头文件，输入输出流？

 iostream

 输入：cin

 输出：cout

### 2、命名空间

  使用命名空间的关键字：using

  命名空间关键字：namespace

  命名空间标准库：std

### 3、C++扩展名

  .cpp

### 4、注释

单行注释：//

多行注释：/*...*/

### 5、动态内存的分配与释放

  申请空间：new

  释放空间：delete

### 6、作用域

  ::

### 7、引用:&

  引用的作用：为某变量取别名（取值同步）

### 8、const应用（常量，与指针一起使用，函数末尾）

（1）定义常量（有了初始值后取值不再发生改变）：

   const double PI=3.14;

（2）const与指针一起使用：

指向常量的指针：变量的值不能改，地址可改

int x=10;

int const *p=&x;

常指针：值能改，地址不能改

int *const p=&x;

指向常量的常指针：值和地址都不能改

int const *const p=&x;

（3）函数末尾加const

![img](file:///C:/Users/26371/AppData/Local/Temp/msohtmlclip1/01/clip_image002.png)

### 9、内联函数

  关键字：inline

  不适合：复杂的程序(循环结构+选择结构+函数的递归)

适合：1-5行代码

### 10、外联函数

在类内声明，在类外实现（加作用域，类名::函数名）

属于类内成员

### 11、带默认参数的函数

  函数参数默认值顺序**自右而左**，不能跳跃

void fun(int a,int b,int c=5){}

void fun(int a,int b=3,int c=5){}

void fun(int a=1,int b=3,int c=5){}

void fun(int a=1,int b,int c=5){} 错误

### 12、函数重载

  多个函数名相同，但是参数必须不同

（1）或者类型不同

（2）或者个数不同

（3）或者顺序不同

### 13、函数模版

定义模版的关键字：template

定义模版类型的关键字：typename或class

template<typename T>或者：

template<class T>

void f(){}

### 14、类和对象的关系

  对象是类的实例，类是对象的模版/抽象

### 15、对象的定义(普通对象，指针对象)

![img](file:///C:/Users/26371/AppData/Local/Temp/msohtmlclip1/01/clip_image004.png)

### 16、this指针：

 

```c++
#include <iostream>
using namespace std;
class Stu{
private:
    string name;
    int age;
public:
    //构造函数 
    Stu(string name,int age){
        this->name = name;//this调用的是成员变量 
        this->age = age;
    }
  
};
int main(){

}
```



### 17、拷贝构造函数（赋值，对象为参数）

```c++
 Stu(Stu &stu){}//拷贝构造函数，参数是对象的引用
```

调用拷贝构造函数的时机

1. 当一个对象赋值给另一个同类型的对象时

   ```c++
   Stu s1;
   Stu s2 = s1;自动调用拷贝函数
   ```

2. 当一个对象赋值给另一个同类型的对象时

   ```c++
   Stu s1;
   Stu s2(s1)
   ```

3. 当调用参数是对象类型的函数时

   ```c++
   void f(Stu s){}
   main(){
       Stu s1;
       f(s1);//自动调用拷贝构造函数
   }
   ```

   



### 18、静态成员

- 关键字：**static**
- 静态变量**不能**在类内初始化，在**类外赋值**，能被**所有对象**共享，取**最近一次**赋值
- 静态函数能调用：**静态成员**+**全局变量**+**常量**(const)
- 静态成员能被对象名调用，也可以被类名直接调用：(Stu::f())，建议类名调用
- 实例成员(**非静态**)能被对象名调用，但不能被类名调用

### 19、友元

-  关键字:**friend**
- 友元分三类：
  - **友元函数**
  - **友元成员**
  - **友元类**
- 友元**不属于**类中成员，可以调用类中所有成员
- 友元函数，在类内声明，类外实现（不加作用域）

### 20、继承的三种方式

 继承符号

```c++
：
```

- public公有继承：子类继承父类成员的权限在子类中不变
- protected受保护的继承：子类继承父类的成员权限在子类中都是受保护的，本类和子孙后代
- private私有继承：子类继承父类的成员的权限在子类中都是私有的
- 默认继承方式：private

### 21、多继承

 一个子类可以继承多个父类，一个父类可以有多个子类，父:子=m:n

### 22、构造函数和析构函数（临时对象不需要时）P57+P76

#### 区别

- 没有返回值
- 无法被继承
- 构造函数可以有默认值
- 析构函数可以加virtual
- 构造函数可以重载，析构函数无法重载

#### 析构函数

- 不能指定任何的返回类型
- 析构函数没有参数
- 析构函数的函数名类名前加~，其他和构造函数相同
- 用来释放空间
- 可以主动调用，可以自动调用
  - 使用delete删除对象
  - 程序结束
  - 临时对象不需要的时候

### 23、虚基类

-  关键字：virtual
- 作用：消除二义性

### 24、类模板

```c++
temolate<typename T>
temolate<class T>
    
Class ...
```

模板**类**是类**模板**的实例

### 25、多态性的实现有三种方式：

####  函数重载



#### 运算符重载

实质上是函数重载



#### 虚函数



### 26、运算符重载

- 所有运算符重载函数名称：operator
- 重载为类的成员函数
  - 双目运算符重载函数，有一个参数（this，（））
  - 前置单目运算符，有0个参数
  - 后置单目运算符，有一个参数（int）
- 重载为类的非成员函数（用友元函数实现）



### 27、虚函数

关键字：virtual

作用：用于子类重写父类函数，子类重写父类函数后，默认也是虚函数，virtual可省略，从而实现多态性。

实现多态性的方式是：通过父类的指针变量或引用调用子类重写的方法。 

### 28、纯虚函数

   virtual void study()=0;//定义纯虚函数

  纯虚函数没有方法体，只在类内声明。

### 29、抽象类

 （1）至少含有一个纯虚函数的类就是抽象类

（2）抽象类不能实例化，即：不能对抽象类创建对象

（3）抽象类用作父类(基类)

### 30、输入输出流运算符重载

 输入运算符重载：istream, >>

输出运算符重载：ostream, <<

### 31、文件的读写

 （1）加载的头文件：fstream

（2）fstream有2个子类：ifstream(读取文件)，ofstream(写入数据)

（3）打开文件函数：open()

（4）关闭文件函数：close()

### 32、异常处理

 （1）可能的错误代码放在：try

（2）捕获异常：catch

（3）抛出异常：throw

## 二、阅读

### 1、函数重载

#### 1

```c++
void area()
{
    cout<<"game over\n";
}

int area(int width,int height)
{
    return width*height;
}

int area(int length,int width,int height)
{
    return width*height*length;
}
int main() 
{
    area();
    cout<<area(5,10)<<endl;
    cout<<area(3,4,5)<<endl;
    return 0; 
}
```

 **输出：**

```
game over
50
60
```

#### 2

```c++
void calculate(int a, int b) {
    cout << "Product: " << a * b << endl;
}
void calculate(double a, double b) {
    cout << "Product: " << a * b << endl;
}

void calculate(int a, double b) {
    cout << "Product: " << a * b << endl;
}

void calculate(double a, int b) {
    cout << "Product: " << a * b << endl;
}

int main() {
    calculate(2, 3);
    calculate(2.5, 3.5);
    calculate(2, 3.5);
    calculate(2.5, 3);
    return 0;
}
```

**输出：**

```
Product: 6
Product: 8.75
Product: 7
Product: 7.5
```

#### 3

```c++
#include <iostream>
using namespace std;
void show(int a) {
    cout << "Integer: " << a << endl;
}
void show(double a) {
    cout << "Double: " << a << endl;
}
void show(char a) {
    cout << "Character: " << a << endl;
}

void show(string a) {
    cout << "String: " << a << endl;
}

int main() {
    show(10);
    show(10.5);
    show('A');
    show("Hello");
    return 0;
}
```

**输出：**

```
Integer: 10
Double: 10.5
Character: A
String: Hello
```



### 2、变量的引用

（1）

```c++
int main() {
    int x = 10;
    int &ref = x;
    ref = 20;
    cout << "x = " << x << endl;
    cout << "ref = " << ref << endl;
    return 0;
}
```

（2）

```c++
void increment(int &ref) {
    ref++;
}
int main() {
    int a = 5;
    increment(a);
    cout << "a = " << a << endl;
    return 0;
}
```

（3）

```c++
int main() {
  int a = 5;
  int &r1 = a;
  int &r2 = r1;
  r2 = 10;
  cout << "a = " << a << endl;
  cout << "r1 = " << r1 << endl;
  cout << "r2 = " << r2 << endl;
  return 0;
}
```

```
a = 10
r1 = 10
r2 = 10
```

（4）

```c++
void swap(int &x, int &y) {
  int temp = x;
  x = y;
  y = temp;
}
int main() {
  int a = 5, b = 10;
  swap(a, b);
  cout << "a = " << a << endl;
  cout << "b = " << b << endl;
  return 0;
}
```

```
a = 10
b = 5
```

（5）

```c++
void update(int &ref) {
  ref = ref * 2;
}
int main() {
  int num = 10;
  update(num);
  cout << "num = " << num << endl;
  return 0;
}
```

```
num = 20
```

（6）

```c++
int main() {
  int a = 4;
  int b = 6;
  int &ref = a;
  ref = b;
  cout << "a = " << a << endl;
  cout << "b = " << b << endl;
  cout << "ref = " << ref << endl;
  return 0;
}
```

```
a = 6
b = 6
ref = 6
```



### 3、构造函数与析构函数执行顺序

（1）

```c++
#include <iostream>
using namespace std;
class Test {
    public:
    Test() {
        cout << "Constructor called" << endl;
    }
    ~Test() {
        cout << "Destructor called" << endl;
    }
};
int main() {
    Test obj;
}
```

```
Constructor called
Destructor called
```

（2）

```c++
class MyClass {
public:
  MyClass() {
    cout << "Constructor called" << endl;
  }
  ~MyClass() {
    cout << "Destructor called" << endl;
  }
};
int main() {
   MyClass obj;
  cout << "Function ended" << endl;
  return 0;
}
```

```

```

（3）

```c++
class MyClass {
    public:
    MyClass() {
        cout << "Constructor called" << endl;
    }
    ~MyClass() {
        cout << "Destructor called" << endl;
    }
};
void func() {
    MyClass obj;//局部变量
}
int main() {
    func();//调用函数结束后，系统自动执行析构函数，释放局部对象的空间
    cout << "Function ended" << endl;
    return 0;
}
```

```
Constructor called
Destructor called
Function ended
```

在C++中，当一个对象被创建时，会调用其构造函数。在这个例子中，当`MyClass`对象`obj`被创建时，会输出"Constructor called"。

然后，当函数`func`结束时，`obj`对象的生命周期结束，会调用其析构函数。析构函数会输出"Destructor called"。

最后，在`main`函数结束时，会输出"Function ended"。

这个顺序是由于C++的作用域规则决定的。在`func`函数内部定义的`obj`对象，其生命周期与`func`函数的执行周期相同。当`func`函数执行结束时，`obj`对象也被销毁。

（4）

```c++
#include <iostream>
using namespace std;
class Number {
    int value;
    public:
    Number(int v) : value(v) {
        cout << "Constructor called with value: " << value << endl;
    }
    ~Number() {
        cout << "Destructor called for value: " << value << endl;
    }
};
int main() {
    Number num1(10);
    Number num2(20);
    return 0;
}
```

```
Constructor called with value: 10
Constructor called with value: 20
Destructor called for value: 20
Destructor called for value: 10
```

在这个例子中，我们创建了两个`Number`对象`num1`和`num2`，并在构造函数中传入了不同的值。当`num1`和`num2`在`main`函数结束时被销毁时，会调用相应的析构函数，并输出它们的值。

注意，析构函数的调用顺序与对象的创建顺序相反。这是因为C++的析构函数调用遵循“后进先出”（LIFO）的原则。

（5）

```c++
class Box {
public:
  Box() {
    cout << "Default Constructor called" << endl;
  }
  Box(int length, int width) {
    cout << "Parameterized Constructor called with length " << length << " and width " << width << endl;
  }
  ~Box() {
    cout << "Destructor called" << endl;
  }
};
```

（6）

```c++
#include <iostream>
using namespace std;
class Data {
public:
  Data() {
    cout << "Default Constructor" << endl;
  }
  ~Data() {
    cout << "Destructor" << endl;
  }
};
int main() {
  Data d1;
  Data d2 = d1;
  return 0;
}
```

（7）

```c++
#include <iostream>
using namespace std;
class Example {
public:
  Example() {
    cout << "Default Constructor" << endl;
  }
  Example(const Example &e) {
    cout << "Copy Constructor" << endl;
  }
  ~Example() {
    cout << "Destructor" << endl;
  }
};
int main() {
  Example e1;
  Example e2 = e1;
  return 0;
}
```



 （8）

```c++
class A {
  public:
    A() {
      cout << "A" << endl;
    }
    ~A() {
      cout << "~A" << endl;
    }
};
class B: A {
  public:
   B() {
      cout << "B" << endl;
    }
    ~B() {
      cout << "~B" << endl;
    }
};
int main() {
  A a;
  B b;
}
```

```
A
A
B
B
A
A
```

（9）

写出下面程序的运行结果。

```c++
class T{

    public:
    T(){
        cout<<"T构造\n"; 
    } 
}; 
class A{
    public:
    A(){
        cout<<"A构造\n";
    }
};
class B: public A{
    public:
    B(){
        cout<<"B构造\n";
    }
    private: 
    T t;
};
int main(){
    B b;
    return 0;
} 
```

```
A构造
B构造
T构造
```

在这个例子中，我们有一个基类`A`和一个派生类`B`，`B`类中有一个成员变量`t`，类型为`T`。

当我们创建`B`类的对象`b`时，首先会调用基类`A`的构造函数，然后调用派生类`B`的构造函数，最后调用`T`类的构造函数。

这是因为在C++中，对象的构造和销毁顺序是从基类到派生类，然后是成员变量。这种顺序也被称为“构造函数的调用顺序”。

### 4、局部变量、成员变量、全局变量

```c++
class A {
    protected:
    int x = 10;
};
class B : A {
    public:
    void Show() {
        int x = 6;
        cout << this->x;
        cout << A::x ;
        cout << x ;
    }
    private:
    int x = 3;
};
int main() {
    B b;
    b.Show();
    return 0;
}
```

```
3
10
6
```



## 其他

### 运算符

```c++
int main(){
    int x = 5;
    x+=x-=x*=8;
    cout<<x;
}
```

```c++
int main(){
    int x = 5;
    x = x * 8;//x=40
    x = x - x;//x=40-40
    x = x + x;//x=0+0
    cout<<x;
}
```

自右向左，每次带入最近的x取值，x为0

### 数学函数

```c++
int main(){
    cout<<abs(-8)<<endl;//求绝对值
    cout<<sqrt(169)<<endl;//开根号
    cout<<pow(4,3)<<endl;//求4的3次方
    cout<<max(-1,-6)<<endl;//求最大值
    cout<<min(-1,-6)<<endl;//求最小值
    cout<<ceil(4.2)<<endl;//向上取整
    cout<<floor(4.8)<<endl;//向下取整
    cout<<round(4.4)<<endl;//四舍五入取整
}
```

## 程序

编写一个程序，创建一个Person类，包含姓名和年龄两个属性，并实现这个类的构造函数和输出信息的成员函数。

```c++
#include<iostream>
using namespace std;

class Person{
    private:
        string name;
        int age;
    public:
        Person(string name,int age):name(name),age(age){}
        void display(){
            cout<<"姓名:"<<name<<"年龄:"<<age<<endl;
        }
};
```

编写一个程序，创建一个Book类，包含书名、作者和价格三个属性，并实现这个类的构造函数和输出信息的成员函数。

```c++
#include<iostream>
using namespace std;

class Book{
  	private:
        string name;
        string author;
        double price;
    public:
        Book(string name,string author,double price):name(name),author(author),price(price){}
        void display(){
            cout<<name<<author<<price<<endl;
        }
};
```

编写一个程序，创建一个Music类，包含歌曲名称、歌手和时长三个属性，并实现这个类的构造函数和输出信息的成员函数。

```c++
#include<iostream>
using namespace std;

class Music{
	private:
    	string name;
    	string singname;
    	string time;
    public:
    	Music(string n,string s,string t):name(n),singname(s),time(t){}
    	void display(){
            cout<<name<<singname<<time<<endl;
        }
}
```



### 抽象类、纯虚函数，实现多态性

抽象类是一种不能被实例化的类，只能作为其他类的基类使用。抽象类中可以包含普通成员函数，也可以包含纯虚函数。纯虚函数是一种没有具体实现的函数，它的功能由派生类来实现。
虚函数的主要作用是实现多态。多态是指一个类的函数在它的派生类中有不同的实现，当通过基类指针或引用调用这个函数时，会调用派生类的实现。
抽象类的主要作用是为一组相关的类提供一个通用的接口。通过抽象类，我们可以将一些公共的成员函数和成员变量放在一起，使得派生类可以共享这些成员，同时也可以通过纯虚函数强制派生类提供特定的实现。



创建一个抽象类 Food，包含两个纯虚函数 getTaste() 和 getTexture()，分别返回食物的口感和质地。创建一个 Cake 类和一个 Pizza 类，分别继承 Food 类并实现其 getTaste() 和 getTexture() 函数。

```c++
#include<iostream>
using namespace std;
class Food{
  public:
    virtual void getTaste()=0;
    virtual void getTexture()=0;
};
class Cake:public Food{
    public:
    virtual void getTaste{
        cout<<"非常甜"<<endl;
    }
    virtual void getTexture(){
        cout<<
    }
}

int main(){
    Food *f = new Cake;
    f->getTaste();//通过父类的指针调用子类重写的方法
    f->getTextture();
    f = new Pizza();
    f -> getTaste();
    f->getTexture();
    
    Cake c;
    c.getTaste();
    
    
    pizza cc;
    cc.getTaste();
}
```

 创建一个抽象类 Person，包含一个纯虚函数 getRole()，返回人员职务。创建一个 Teacher 类和一个 Student 类，分别继承 Person 类并实现其 getRole() 函数。



创建一个抽象类 Animal，包含一个纯虚函数 eat()，表示动物进食。创建一个 Herbivore 类和一个 Carnivore 类，分别继承 Animal 类并实现其 eat() 函数。



创建一个抽象类 S，包含一个纯虚函数 area()，表示计算面积。创建一个 Circle 类和一个 Square 类，分别继承 Shape 类并实现其area() 函数,输出圆和正方形的面积。



运算符重载函数

（1）普通运算符重载：

重载加法运算符 +，用于两个对象相加。

重载减法运算符 -，用于两个对象相减。

重载乘法运算符 *，用于两个对象相乘。

重载除法运算符 /，用于两个对象相除（假设除数不为零）。

（2）输入输出运算符重载

①　输入输出某个坐标信息

②　输入矩形长和宽，求周长、面积

③　输入梯形上底、下底、高，计算面积

文件操作

对象数组的应用

异常处理





