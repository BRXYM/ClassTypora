# C++

## 第一章 概述

C++是一个**面向对象编程**的语言



### 重载

包括**函数重载**和**运算符重载**



### 面向对象程序设计方法的优点

1. 面向对象程序设计可提高程序的重用性
2. 面向对象程序设计可控制程序的复杂性
3. 面向对象程序设计可改善程序的可维护性
4. 面向对象程序设计能够更好地支持大型程序设计
5. 面向对象程序设计增强了计算机处理信息的范畴
6. 面向对象程序设计能很好地适应新的硬件环境



## 第二章 C++语言

### 输入与输出

标准输出流对象cout

cout数据先出送到缓冲区，然后到控制台

```cpp
cout<<表达式<<表达式;
cout<<"Hello\n";
//输出Hello并换行
cout<<endl;
//换行
```



标准输入流对象cin

```cpp
cin>>表达式>>表达式;
cin>>a>>b;
//输入a和b的，两数之间拿空格分隔
```



cerr

数据不经过缓冲出，直接输送到控制台

### 变量的定义

```c++
    int x = 10;//定义一个局部变量
    cout << x << endl;//就近原则，取局部变量的值
    int y = ::x + x;//::寻找全局变量
    cout << y << endl;
```



### 命名空间

使用**namesapce**建立空间。

#### 嵌套命名空间

```c++
namespace n1{
    namespace n2{
        int x = 5,y = 6;//命名空间的变量初始化要一体
        int f(){
            int z = x*y;
            return z;
        }
    }
}
```



#### 调用命名空间

```c++
int main(){
    using n3::g;
    g();
    
}
```



### 强制类型转换

```c++
    int x = 4, y, z;
    double a = 3.56, b, c;
    b = x;//自动类型转换
    cout << b << endl;
    cout << "你好";
    y = a;//高精度到低精度自动类型转换，不存在四舍五入
    cout << y << endl;
    z = (int) a;
    cout << z << endl;
    z = int(a);
    cout << z << endl;
```



### 动态内存空间的分配和释放

```c++
   	int *p;
    p = new int;
    *p = 200;
    cout<<p<<","<<*p<<endl;
    int *t = new int;
    *t = 100;
    cout<<t<<","<<*t<<endl;//t：地址，*t：值
    //为指针分配空间一体化（包含赋值）
    int *s = new int(250);
    cout<<s<<","<<*s<<endl;
    delete p;//释放空间
    delete t;//释放空间
    delete s;//释放空间
```



#### 静态创建数组

```c++
    int a[5];//没有初始化时，数组的长度不可以省略
    int b[] = {3,5,6,7};//初始化后，数组的长度可以省略
    int c[10] = {3,5,6,7,8};//大于等于实际元素个数
    cout<<sizeof(b)<<endl;//4*4 16内存空间
    cout<<sizeof(c)<<endl;//4*10 40内存空间
```



#### 动态创建数组

```c++
int *p = new int[5];
```



#### 释放空间

```c++
    delete []p;//释放空间，区分数组
```



### 引用

```c++
    int x = 10, y = 3;
    int &m = x;
    cout << "x=" << x << ",m=" << m << endl;
    x = 20;
    cout << "x=" << x << ",m=" << m << endl;
    m = 30;
    cout << "x=" << x << ",m=" << m << endl;
```

- 定义引用时初始化一定是**某个变量**的名字
- 引用就是为某**变量取别名**，应用于初始化的变量取值
- 定义引用时**一定初始化**（一体化）



#### 引用用于方法的传参

```c++
#include "bits/stdc++.h"
using namespace std;
void change(int &x,int &y){
    int t = x;
    x = y;
    y = t;
}
int main(){
    int a = 4,b = 8;
    cout<<"调用函数前";
    cout<<"a = "<<a<<",b = "<<b<<endl;
    change(a,b);
    cout<<"调用函数后";
    cout<<"a = "<<a<<",b = "<<b<<endl;
    return 0;
}
```

在change中，x为a的别名，y为b的别名



### 常量及指针

```c++
    int x = 10, y = 20;
    const int *p = &x;//定义指向常量的指针变量
    cout << *p << endl;
    p = &y;//可以改地址
    cout << *p << endl;
    //*p = 100;error;不能改值
    //2 -- 常指针
    int *const t = &x;
    cout << *t << endl;
    // t = &y;error:不能改地址
    *t = 50;
    cout << *t << endl;
    cout << x << endl;
    //指向常量的长指针
    const int *const s = &x;
    cout << *s << endl;
    //双长指针既不能改地址也不能改值
    //s = &y;不能改地址
    //*s = 250;不能改值
```



### 字符串

```c++
    string s1 = "你猜我会写什么", s2("不知道啊不知道");
    string s3 = "lovemoon";
```



#### 获取字符串的长度size,length

```c++
    cout << s1.size() << endl;
    cout << s1.length() << endl;
```



#### 向字符串中插入数据append,insert

```c++
   	cout << s1.append("因为可爱") << endl;//在末尾追加
    cout << s1.insert(2, "hello") << endl;
```

可以在任意位置追加，按照编码占的空间选择，GBK中文字符为2，utf-8中文字符为3



#### 字符串的比较compare

```c++
 	cout << s2.compare("cat") << endl;//对应位进行ASCII码值的比较
	//前串如果大于后串，输出1
    cout << s2.compare("moon") << endl;
    //前串小于后串，输出-1
    cout << s2.compare(s2) << endl;
    //前串等于后串，输出0
    cout << s2.compare("love") << endl;
    cout << s3.compare("kitty love") << endl;
    string s4 = "安全", s5("中国");
    cout << s1.compare(s5) << endl;//中文比较拼音，对应字符作比较
    cout << s1.compare(s5) << endl;
```



#### 字符串的查找find

```
	string str1 = "love moon";
    cout << str1.find("o") << endl;//从字符左而右查找，第一次出现的下标
    cout << str1.find("o", 2) << endl;
    cout << str1.rfind("o") << endl;//reverse：逆序自右向左
    cout << str1.rfind("o", 5) << endl;//从下标为4处向左查找
```



#### 字符串的替换replace

```c++
    string str2("i love HuTao");
    cout << str2.replace(2, 4, "marry") << endl;
    //[begin index,n,value]从下标为2处开始的四个字符被marry替换
```



#### 字符串的截取substr

```c++
    cout << str1.substr(5) << endl;//[start index]从下标为5开始截取，默认到最后
    cout << str1.substr(0, 4) << endl;//[start index,n]从下标为0开始截取，4个字符
```



#### 删除字符串erase,clear

```c++
    str1.erase();//默认全部是删除
    cout << "str1:" << str1 << endl;
    str2.erase(2);//[begin index]，从下表为2开始删除，到最后
    cout << "str2:" << str2 << endl;
    string str3 = "love honey";
    str3.erase(4, 3);//[begin index,n]:从下标为4开始删除3个
    cout << "str3:" << str3 << endl;
    str3.clear();//无参，全部删除
    cout << "str3:" << str3 << endl;
```



### C++语言中的心特性

#### 内联函数

提高程序的运行效率

```c++
#include "iostream"
void f(int x, int y);
using namespace std;

void f(int &x, int &y) {
    swap(x, y);//交换数据
}

int main() {
    int a = 3, b = 5;
    cout << "调用之前：a=" << a << ",b=" << b << endl;
    f(a, b);
    cout << "调用之后：a=" << a << ",b=" << b << endl;
}


```



#### 参数带默认值的函数

```c++
#include "iostream"
using namespace std;
void add(int x = 6,int y =6){
    cout<<x+y<<endl;
}
int main(){
    add();//默认值
    add(8);//x赋值
    add(7,8);//按照顺序赋值
}
```



#### 函数重载

```c++
#include "bits/stdc++.h"

using namespace std;

void f() {
    cout << "one para" << endl;
}

void f(int x) {
    cout << "one para" << endl;
}

void f(int x, double y) {
    cout << "two1 para" << endl;
}

void f(double x, int y) {
    cout << "two2 para" << endl;
}

int f(int x, int y, int z) {
    cout << "three paras" << endl;
    return x + y + z;
}

int main() {
    f();
    f(20);
    f(3.5, 8);
    f(3, 8.0);
    cout << f(3, 8, 0) << endl;

}
```

- 函数重载，多个方法名字相同，但是残蚀必须不同。
- 个数不同、类型不同、顺序不同
- 函数返回值类型不参与比较
- 函数重载与带默认值的函数共同使用时，可能会引起二义性



#### 函数模板

```c++
#include "bits/stdc++.h"

using namespace std;

template<typename T>
//T:任意数据类型
//获取数组人以数据类型的最小值
T minValue(T a[], int n) {
    T min = a[0];
    for (int i = 0; i <n-1; ++i) {
        if(min>a[i]){
            min = a[i];
        }
    }
    return min;
};

int main() {
    int a[] = {3, 5, 1, 9, 0};
    cout << "a数组的最小值是" << minValue(a, 5) << endl;
    double *t = new double[4]{3.5, 6, 2.7, 5};
    cout << "t数组的最小值" << minValue(t, 4) << endl;
    return 0;
}
```



## 第三章 类与对象

主函数中，只能调用类中**共有成员**

### 类

#### 创建类与对象

```c++
#include "iostream"

using namespace std;

class Student {//成员函数或数据成员默认权限是private
private://定义三个数成员(可以缺省private)
    string name;
    int sno;
    int age;
public:
    //自定义函数，为数据成员初始化
    void set(string n, int s, int a) {
        name = n;
        sno = s;
        age = a;
    }

    //输出学生基本信息
    void show() {
        cout << "name is:" << name << " sno is:" << sno << " age is" << age << endl;
    }
} s1, s2;//定义两个对象s1,s2

int main() {
    Student s;//创建实例
    s.set("胡桃", 123, 18);
    s.show();
    s1.set("钟离", 123, 40);
    s1.show();
}
```

#### 创建对象方法

- 在方法中实例
- 在类后创建

#### this指针的使用

指向当前对象的指针使用方式

- this->成员
- (*this).成员

```c++
#include "iostream"

using namespace std;

class Course {
private:
    string cname;
    string cno;//课程号
    double credit;//进修学分

public:
    void set(string cname, string cno, double credit) {
        this->cname = cname;
        this->cno = cno;
        (*this).credit = credit;
        //this:指向当前对象的指针，使用方式this->成员，或:(*this).成员
    };

    void show() {
        cout << "课程名：" << cname << "，课程号：" << cno << ",学分：" << credit << endl;
    }
} c1, c2;

int main() {
    Course c3;
    c1.set("C++", "101", 4);
    c1.show();
    c2.set("JavaWeb", "102", 4);
    c2.show();
    c3.set("Python", "103", 4);
    c3.show();
}
```



#### 内联函数和构造函数

```c++
#include "iostream"

using namespace std;

class Student {
private:
    string sName;
    int sNo;
    int age;
public:
    /*
     * 构造函数，无返回值类型，与类同名，用于初始化数据成员，可以重载
     * 创建对象时，系统自动调用构造函数
     * 若类体中没有像i按时的定义过任何狗在函数，系统会提高一个默认无参的构造函数
     * 若类体中已经显示的定义过构造函数，系统不会再提供任何构造函数
     */
    Student(string sName, int sNo, int age) {//构造函数(隐式内联函数)
        this->sName = sName;
        this->sNo = sNo;
        (*this).age = age;
    }

    Student() {}//隐式内联函数


    void show() {
        cout << "姓名:" << sName << ",学号:" << sNo << ",年龄:" << age << endl;

    }

    //成员函数若在类内定义并实现，若无inine，成为"隐式内联函数/内联函数/内部函数/内置函数"
    inline void study();//显示内联函数，只在类内声明
} s1("胡桃", 1, 18), s2("钟离", 2, 500);
//创建对象时自动带参数的构造函数

inline void Student::study() {//类内函数在类外实现，显示的加inline，它是(内联函数)
    cout << "阿弥诺斯" << endl;
}

int main() {
    Student s3("心海", 3, 20);
    s1.show();
    s2.show();
    s3.show();
    Student *p = new Student;//创建指针对象，系统自动调用无参构造函数
    Student *t = new Student();//创建只针对象，系统自动调用无参构造函数
    Student *s = new Student("一斗", 4, 200);
    s->show();
    s->study();
}
```

构造函数：无返回值类型，与类同名，用于初始化数据成员，可以重载

创建对象时，系统自动调用构造函数

若类体中没有定义过的构造函数，系统会默认调用一个无参的构造函数

若类体中已经定义过构造函数，系统不hi提供任何构造函数



#### 外联函数

```c++
#include "iostream"

using namespace std;

class Student {
private:
    string sName;
    int sNo;
    int age;
public:
    Student(string sname, int sno, int age);//声明成员函数
    void show();//声明成员函数
    //类内声明函数(无inline),在类体之外实现函数，成为"外联函数"
};

Student::Student(std::string sname, int sno, int age) {
    this->sName = sname;
    this->age = age;
    this->sNo = sno;
}
void Student::show(){
    cout << "姓名:" << sName << ",学号:" << sNo << ",年龄:" << age << endl;
}
int main(){
    Student s1("心海", 3, 20);
    s1.show();
    Student *s2 = new Student("胡桃",1,18);
    s2->show();
}
```



#### 格式化

```c++
#include "bits/stdc++.h"

using namespace std;

int main() {
    int x = 3, y = 5;
    double a = 111.114514, b = 114.114514, c;
    c = a + b;
//    cout << c << endl;
    printf("%.2f\n", c);
    cout << setprecision(4) << c << endl;
    //单独使用setprecision(4)<<c<<endl;

    cout << fixed << setprecision(2) << c << endl;
    //用fixed与setprecision(n)联用:n表示小数部分的位数

    cout << setw(5) << x;
    cout << setw(5) << y << endl;
    //setw(n)总共占n位,不够默认空格补齐,默认右对齐

    cout << setiosflags(ios::left) << setw(5) << x;
    cout << setiosflags(ios::left) << setw(5) << y << endl;
}
```



### 对象

#### 对象数组

数组传入参数的两种方式

```c++
#include <iostream>
using namespace std;
class Student{
private:
    string sname;
    int sno;
    int age;
public:
    void set(string snaem,int sno,int age){
        this->sname = snaem;
        this->sno = sno;
        this->age = age;
    }
    void show(){
        cout<<"姓名:"<<sname<<",学号:"<<sno<<",年龄:"<<age<<endl;
    }
};
int main(){
    Student s[3];//创建对象数组，里面有3个对象
    s[0].set("胡桃",101,18);
    s[1].set("心海",102,22);
    s[2].set("宵宫",103,20);
    for (int i = 0;i<3;i++){
        s[i].show();
    }
}
```

```c++
#include <iostream>

using namespace std;

class Student {
private:
    string sname;
    int sno;
    int age;
public:
    Student(string snaem, int sno, int age) {
        this->sname = snaem;
        this->sno = sno;
        this->age = age;
    }

    void show() {
        cout << "姓名:" << sname << ",学号:" << sno << ",年龄:" << age << endl;
    }
};

int main() {
    Student s[3] = {Student("胡桃", 101, 18),
                    Student("心海", 102, 22),
                    Student("宵宫", 103, 20)};
    //创建对象数组，里面有3个对象
    for (int i = 0; i < 3; i++) {
        s[i].show();
    }
}

```



#### 对象数组键盘赋值

```c++
#include <iostream>

using namespace std;

class Student {
private:
    string sname;
    int sno;
    int age;
public:
    Student(string snaem, int sno, int age) {
        this->sname = snaem;
        this->sno = sno;
        this->age = age;
    }
    Student(){}//定义无参构造函数，解决后面创建空对象的问题

    void show() {
        cout << "姓名:" << sname << ",学号:" << sno << ",年龄:" << age << endl;
    }
};

int main() {
     //2-从键盘为对象数组赋值

    Student s[3];
    string sname;
    int sno;
    int age;
    for (int i = 0; i < size(s); ++i) {
        cout<<"第"<<i+1<<"个,请输入学生信息(姓名,学号,年龄):";
        cin>>sname>>sno>>age;
        s[i]=Student(sname,sno,age);
    }
    for (int i = 0; i < size(s); i++) {
        cout<<"第"<<i+1<<"个:";
        s[i].show();
    }
}
```



#### 数据成员初始化

##### 构造函数初始化方式一

```c++
Animal(string name, string type, int age) {
    this->name = name;
    this->type = type;
    this->age = age;
}
```

##### 构造函数初始化方法二

```c++
Animal(string n,string t,int a):name(n),type(t),age(a){}
```

##### 构造函数初始化方法三

```c++
Animal(string name,string t,int a):name(name),type(t),age(a){}
```



```c++
#include "iostream"

using namespace std;

class Animal {
private:
    string name;
    string type;
    int age;
public:
    //构造函数初始化方式一
//    Animal(string name, string type, int age) {
//        this->name = name;
//        this->type = type;
//        this->age = age;
//    }
//    void show();

    //构造函数初始化方法二
//    Animal(string n,string t,int a):name(n),type(t),age(a){
//    }
//    构造函数初始化方法三
    Animal(string name,string t,int a):name(name),type(t),age(a){
    }
//    签名行对数据成员初始化的方式只适合于构造函数，普通方法不可以

    Animal(){}
    void show();
};

//外联函数
void Animal::show() {
    cout << "名称:" << name << ",类型:" << type << ",年龄:" << age << endl;
}

int main() {
    //创建对象数组，四个对象，初始化并输出各自信息
    Animal animal[4];
    string name;
    string type;
    int age;
    for (int i = 0; i < size(animal); ++i) {
        cout << "第" << i + 1 << "个,请输入动物信息(名称,类型,年龄):";
        cin >> name >> type >> age;
        animal[i]=Animal(name,type,age);
    }
    for (int i = 0; i < size(animal); ++i) {
        animal[i].show();
    }
}
```



### 构造函数及析构函数

```c++
#include "iostream"

using namespace std;

class A {
    public:
    A() {//定义构造函数
        cout << "A构造函数" << endl;
    }

    ~A() {//没有参数，没有返回值
        cout << "A析构函数" << endl;
    }
};

class B {
    public:
    B() {
        cout << "B构造函数" << endl;
    }

    ~B() {
        cout << "B析构函数" << endl;
    }
};

int main() {
    A a;
    B b;
}
```

|          |         |          |            |                  |                        |          |
| -------- | ------- | -------- | ---------- | ---------------- | ---------------------- | -------- |
| 构造函数 | 类名{}  | 带参数   | 允许重载   | 占用内存开辟空间 | 创建对象时系统自动调用 | 新建空间 |
| 析构函数 | ~类名{} | 不带参数 | 不允许重载 | 释放内存         | 文件结束后系统自动调用 | 回收空间 |
|          |         |          |            |                  |                        |          |

 * 共同点：不能有返回值
 * 析构函数的释放顺序是栈规则，先进后出，后进先出
   

#### 含有对象成员的构造函数及析构函数

```
#include "iostream"

using namespace std;

class Student {
public:
    Student() {
        cout << "student构造函数" << endl;
    }

    ~Student() {
        cout << "student析构函数" << endl;
    }
};

class Teacher {
public:
    Teacher() {
        cout << "teacher构造函数" << endl;
    }

    ~Teacher() {
        cout << "teacher析构函数" << endl;
    }
};

class Course {
public:
    Course() {
        cout << "course构造函数" << endl;
    }

    ~Course() {
        cout << "course析构函数" << endl;
    }
private://定义两个对象成员
    Student student;
    Teacher teacher;
};



int main() {
//    Student student;
//    Teacher teacher;
    Course course;
}
```

**含有对象成员的构造函数及析构函数执行顺序：**

- 构造：先执行对象成员的构造函数(自上而下)，后执行自己的构造函数
- 析构：先执行自己的析构函数，后执行对象成员的析构函数(自下而上)
- 构造：相当于队列(FIFO)
- 析构：相当于栈(FILO)

```c++
#include "iostream"

using namespace std;

class Test {
public:
    Test() {//定义构造函数
        cout << "first" << endl;
    }
    Test(Test &test) {//定义拷贝构造函数,参数是对象的引用
        cout << "second" << endl;
    };
};

void f(Test test){//自定义函数，参数是对象类型
    cout << "third" << endl;
}

Test g(){//自定义函数，返回值是对象
    Test test;//创建对象
    return test;//返回对象
}

int main() {
    Test test;//创建对象时系统自动调用构造函数
    Test test1 = test;//对象为对象赋值方式1
    //1--当一个对象赋值给另一个**同类型**对象时,系统自动调用拷贝构造函数
    Test test2(test);//对象为对象赋值方式2
    //2--当一个对象赋值给另一个**同类型**对象时，系统自动调用拷贝构造函数
    f(test);
    //3--当调用参数时对象类型的函数时，系统有优先调用拷贝构造函数,然后执行该方法内其他语句
    test = g();
    //4--当调用返回值时的对象类型的函数时系统会扫描到拷贝构造函数,但是没有去调用
}
```

- 当一个对象赋值给另一个**同类型**对象时，系统自动调用**拷贝构造函数**
- 当调用参数时对象类型的函数时，系统有**优先调用拷贝构造函数**，然后执行该方法内其他语句
- 当调用返回值时的对象类型的函数时，系统会**扫描到拷贝构造函数**，但是**没有去调用**



### 静态成员

```c++
#include "iostream"

using namespace std;
int x = 20;//全局变量
class Student {
private:
    string sname;//没有static修饰，称为实例变量
    int sno, age;
    static string grade;//静态变量(会被所有变量共享)
public:
    Student(string sname, int sno, int age) : sname(sname), sno(sno), age(age) {}

    void show() {//没加static称为实例方法
        cout << sname << "," << sno << "," << age << "," << grade << endl;
    }

    static void f() {//没加static称为实例方法
        cout << x << "," << grade << endl;
    }
};

string Student::grade = "2023级";
//静态成员变量一定要在类体之外初始化

int main() {
    Student student1("胡桃", 1, 22),
            student2("心海", 2, 18),
            student3("宵宫", 3, 19);
    student1.show();
    student2.show();
    student3.show();
    student1.f();//对象名调用静态成员
    Student::f();//类名直接调用静态成员
}
```

- 实例方法，既可以调用静态成员，也可以调用调用实例成员
- 对象调用，不能被类名直接调用
- 静态方法，可以调用静态成员，不可以调用实例成员
- 静态方法，可以被对象调用，又能被类名直接调用，建议用**类名直接调用**，使用对象调用占空间

```c++
#include "iostream"

using namespace std;

class People{
private:
    static int n;
public:
    People(){
        n++;
        cout<<"您是第"<<n<<"个访问系统的人"<<endl;
    }
};
int People::n = 0;
int main() {
    People p1,p2,p3;//创建三个对象，调用三次构造函数
}
```

静态成员变量，初始化一次，它会保留最近一次的取值



### 指针

#### 指向数据成员的指针变量

```c++
#include "bits/stdc++.h"

using namespace std;

class Test {
public:
    int i;
    Test(int n) : i(n) {}
    Test() {}
};

int Test::*p = &Test::i;
//类外定义只想数据成员的指针变量

int main() {
    Test t(5);
    cout << t.i << endl;//对象调用数据成员
    cout << t.*p << endl;//通过类外指针调用数据成员
    t.*p = 20;
    cout << t.i << endl;//*p与i取值同步
    cout << t.*p << endl;
}
```



#### 类外指向数据成员函数的指针变量

```c++
#include "bits/stdc++.h"

using namespace std;

class Test {
private:
    int n;
public:
    void set() {//自定义函数，初始化数据成员
        n = 5;
        cout << n << endl;
    }
    void set(int i){
        n = i;
        cout << n << endl;
    }

};
//void (Test::*t)() = Test::set;
void (Test::*t)() = &Test::set;
void (Test::*k)(int) = &Test::set;//有参数类型就可以
//指向成员函数的指针变量，函数名前可省略&
//方法带括号

int main() {
    Test tt;
    tt.set();//对象调用成员函数
    (tt.*t)();//用指针调用成员函数
    //  1
    Test *p = &tt;
    p->set();//创建指向对象的指针变量
    //  2
    Test *s = new Test;
    s->set();//创建只针对想的指针变量
    (tt.*k)(110);
}
```



#### 类外指向静态成员函数的指针变量

```c++
#include "bits/stdc++.h"

using namespace std;

class Test {
private:
    static int n;
public:
    static void set(int i) {//静态方法
        n += i;
        cout << n << endl;
    }
};

int Test::n = 5;
void (*p)(int) = Test::set;//此处可省略&
//不需要加作用域，类外定义指针静态方法的指针变量

int main() {
    Test::set(10);//15，通过类名直接调用静态方法
    (*p)(6);//15+6，通过指针调用静态方法
    p(9);//21+9，可以省略*
}
```



## 第四章 友元

- 友元提供了不同类成员函数之间，**类成员函数**与**一般函数**之间进行**数据共享**的机制。

- 可以在类体外任何地方，都可以访问**所有成员**包括私有

- 友元是给予，不是索取
- 友元关系既不对称，也不传递
- 友元**不属于类中成员**
- 友元函数的参数一般是**对象引用参数**

**友元的分类**

1. **友元函数**
2. **友元成员**
3. **友元类**

### 友元的定义

声明友元函数，在**类内声明**，**类外实现**方法体

**优点**

- 友元函数并不属于类中成员，它可以访问类中所有所有成员，(重点是private和protected)
- 能够提高程序的运行效率，可以使类与类之间合作共同完成某一任务
- 友元函数一般参数是对象的调用，通过引用类中成员

**缺点**

- 破坏了类的封装性和隐蔽性，尽量少用



### 友元函数

```c++
#include "bits/stdc++.h"

using namespace std;

class Time {
private:
    int hour, minute, second;
public:
    Time(int hour, int minute, int second) : hour(hour), minute(minute), second(second) {}
    Time() {}

    friend void show(Time &t);//声明友元函数
};

void show(Time &t) {//函数参数是对象的引用
    cout << t.hour << ":" << t.minute << ":" << t.second << endl;
}

int main() {
    Time t(11, 30, 35);//创建对象，调用构造函数
    show(t);//调用友元函数，因为不属于类中函数，所以不需要对象调用
}
```

```c++
#include "iostream"

using namespace std;

class Student {
private:
    string sname;
    int sno;
public:
    Student(string sn, int sno) : sname(sn), sno(sno) {}

    Student() {}

    //声明友元函数show
    friend void show(Student &student);

};


void show(Student &student) {
    cout << "姓名:" << student.sname << "学号:" << student.sno << endl;
}

class Score {
private:
    unsigned int chinese, math, english;//无符号整数
public:
    //定义构造函数初始化
    Score(int chinese, int math, int english) : chinese(chinese), math(math), english(english) {}

    Score() {}

    //声明友元函数，display
    friend void display(Student &student, Score &score);
};

void display(Student &student, Score &score) {
    show(student);
    cout << "语文：" << score.chinese << "数学：" << score.math << "英语：" << score.english << endl;
}

int main() {
//    Student student("胡桃",1);//创建学生对象
//    Score score(90,95,80);//创建成绩对象
//
//    display(student,score);
    string sname;
    int sno;
    unsigned int chinese, math, english;//无符号整数

    Student student[3];
    Score score[3];


    for (int i = 0; i < 3; ++i) {
        cout << "请输入第" << i + 1 << "个学生的姓名，学号"<<endl;
        cin >> sname >> sno;
        student[i] = Student(sname, sno);
        cout<<"输入第"<<i+1<<"个学生成绩(c,m,e)"<<endl;
        cin>>chinese>>math>>english;
        score[i] = Score(chinese,math,english);
    }

    for (int i = 0; i < 3; ++i) {
        display(student[i],score[i]);
    }
    
}
```



### 友元成员

```c++
#include "iostream"

using namespace std;

class Date;//声明类

class Time {
private:
    int hour, minute, second;
public:
    Time(int hour, int minute, int second) : hour(hour), minute(minute), second(second) {}

    Time() {}

    void show(Date &date);//声明成员函数
};

class Date {
private:
    int year, month, day;
public:
    Date(int year, int month, int day) : year(year), month(month), day(day) {}

    Date() {}

    friend void Time::show(Date &date);//友元成员
};

void Time::show(Date &date){//友元函数实现，也是类Time的外联函数
    cout<<date.year<<"/"<<date.month<<"/"<<date.day<<"  ";
    cout<<hour<<":"<<minute<<":"<<second<<endl;
}

int main() {
    Date d(2024,4,12);
    Time t(8,58,30);
    t.show(d);//时间对象调用show输出所有
}
```



### 友元类

```c++
#include "iostream"

using namespace std;

class Student {
    friend class Score;

private:
    string name, sno;
public:
    Student(string name, string sno) : name(name), sno(sno) {}
};

class Score {
private:
    int chi, math, eng;
public:
    Score(int chi, int math, int eng) : chi(chi), math(math), eng(eng) {}

    void show(Student &student) {
        cout << "学生姓名" << student.name << "学生学号" << student.sno << endl;
        cout << "语文成绩：" << chi << "，数学成绩：" << math << "，英语成绩：" << eng << endl;
    }
};

int main() {
    Student student[2]={Student("胡桃","101"),Student("心海","102")};
    Score score[2] = {Score(99,88,98),Score(88,98,88)};

    for (int i = 0; i < 2; ++i) {
        score[i].show(student[i]);
    }
}
```



## 第五章 继承

- 共有继承
- 私有继承（**默认继承模式**）
- 受保护继承

### 继承

**默认继承方式**

```c++
#include "iostream"

using namespace std;

class Student{
private:
    string sname;
    int sno;
public:
    Student(){}
    void set(string name,int no){
        sname = name;
        this->sno = no;
    }
    void show(){
        cout<<"姓名："<<sname<<",学号："<<sno<<endl;
    }
};

class SchoolStu:Student{//默认的继承方式是private
private:
    string type;//班级类型（文理）
public:
    void setInfor(string t,string name,int no){
        this->set(name, no);//继承父类中的函数
        type = t;
    }
    void display(){
        this->show();
        cout<<"班级类型："<<type<<endl;
    }
};

class UniversityStu:Student{
private:
    string major;//专业
public:
    void setUS(string name,int no,string m){
        this->set(name,no);//继承父类中的函数
        major = m;
    }
    void print(){
        show();
        cout<<"专业："<<major<<endl;
    }
};

int main() {
    SchoolStu schoolStu;//创建子类对象
    schoolStu.setInfor("理科","胡桃",101);
    cout<<"高中生信息如下："<<endl;
    schoolStu.display();
    UniversityStu universityStu;
    universityStu.setUS("钟离",201,"岩系");
    cout<<"大学生信息如下："<<endl;
    universityStu.print();
}
```



#### 公有继承

- 父类中的私有（**private**）成员变量**无法继承**
- 父类中继承的成员的**权限保持不变**

```c++
#include "iostream"

using namespace std;

class Father {
public:
    string name;//共有属性
protected:
    int age;//受保护的数据成员
private:
    int weight;//私有数据成员
};

class Son : public Father {//共有继承，父类中继承的成员的权限保持不变
public:
    void show() {
        cout << this->name << "," << this->age << endl;
    }
};

class GrandSon : Son {//私有继承
public:
    void display() {//能够继承父类中非私有的成员
        cout << this->name << "," << this->age << endl;
    }
};

int main() {
    Father father;
    father.name;//主函数中，只能调用类中公有成员
    //protected:只能在奔雷及子类类体中使用
    Son son;
    son.name;
//  son.age;
    //error,age是受保护的，无法在父类及子类之外的地方访问
}
```



#### 受保护继承

```c++
#include "iostream"

using namespace std;

class Father {
public:
    string name;//共有属性
protected:
    int age;//受保护的数据成员
private:
    string ID;//私有数据成员
};

class Son : protected Father {//受保护的继承方式，父类中非私有的都可以继承
    //父类中能继承的成员在子类中的权限都变成protected
public:
    void show() {
        cout << this->name << "," << this->age << endl;
    }
};

class GrandSon:Son{
public:
    void display(){
        cout << this->name << "," << this->age << endl;
    }
};


int main() {
    Son son;
    son.show();
    //s.name;error.name在父类Son中权限变成protected，所以无法类外访问
}
```



#### 私有继承

```c++
#include "iostream"

using namespace std;

class Father {
public:
    string name;//共有属性
protected:
    int age;//受保护的数据成员
private:
    string ID;//私有数据成员
};

class Son : private Father {
    //私有的继承方式（private），父类中菲私有的都可以访问父类中能继承的成员在子类中的权限都便曾受保护的（private）
    //父类中name，age在子类中都变成private权限
public:
    void show() {
        cout << this->name << "," << this->age << endl;
    }
};

class GrandSon:Son{
public:
    void display(){
        //name，age在son类中都变成private权限，所以无权访问
//        cout << this->name << "," << this->age << endl;
    }
};

int main() {
    Father father;
    father.name;
    //protected：只能在本来及子类类体中使用    
    Son son;
    son.name;//name权限不足，public
    //son.age;受保护的，无法在父类与子类中调用
    son.show();
    //s.name;error.name在父类Son中权限变成protected，所以无法类外访问
}
```



#### 构造函数初始化

```c++
#include <iostream>

using namespace std;

class Animal {
private:
    string name;
    int age;
public:
    //构造函数初始化
    Animal(string n, int a) : name(n), age(a) {}

    void show() {
        cout << "姓名: " << name << "年龄: " << age << endl;
    }
};

class Cat : public Animal {
private:
    string name;
    int age;
    string type;
public:
    //子类构造函数形参列表:父类构造函数形参列表，子列形参列表
    Cat(string n, int a, string t) : Animal(n, a), type(t) {}

    void display() {//与父类函数同名，隐藏父类的方法(不是重写)
        Animal::show();//调用父类中同名的函数，需要加作用域
        cout << "类型: " << type << endl;
    }
};

class Dog : public Animal {
private:
    string broods;
public:
    Dog(string n, int a, string b) : Animal(n, a), broods(b) {}

    void show_display() {
        Animal::show();
        cout << "类型: " << broods << endl;
    }
};

int main() {
    Cat c("胡桃", 20, "火系");
    c.show();
    Dog d("心海", 20, "水系");
    d.show_display();
}
```



```c++
#include <iostream>

using namespace std;

class A {
private:
    string a;
public:
    A(string a) : a(a) {}

    void show() {
        cout << a << endl;
    }
};

class B {
private:
    string b;
public:
    B(string b) : b(b) {}

    void print() {
        cout << b << endl;
    }
};

class C : public A {
private:
    int c;
    B b;//对象成员
public:
    //子类构造函数形参列表:父类构造形参列表，对象成员形参列表，自己的形参列表
    C(string a, string b, int c) : A(a), b(b), c(c) {}//b(b):通过对象成员引用
    void display() {
        this->show();
        cout << "c=" << c << endl;
        b.print();
        cout << c;
    }
};

int main() {
    B b();
    C c("23", "24", 12);
    c.display();
}
```



#### 析构函数初始化

```c++
#include <iostream>

using namespace std;

class A {
public:
    A() {
        cout << "a\n";
    }

    ~A() {
        cout << "aa\n";
    }
};

class B : public A {
public:
    B() {
        cout << "b\n";
    }

    ~B() {
        cout << "bb\n";
    }
};

class C : public B {
public:
    C() {
        cout << "c\n";
    }

    ~C() {
        cout << "cc\n";
    }
};

int main() {
    //A a;
    //B b;
    //C c;
    //构造函数执行顺序
    //父类构造函数->对象成员的构造函数->子类构造函数
    //A a;
    //B c;(构造函数及析构函数调用过程中与对象名字无关)
    //析构函数执行顺序
    //子类构造函数->对象成员的析构函数->父类构造函数
}
```

#### 含有对象成员的构造函数

```c++
#include "iostream"

using namespace std;

class Score {
private:
    unsigned chi, math, eng;
public:
    Score(unsigned chi, unsigned math, unsigned eng) : chi(chi), math(math), eng(eng) {}

    Score() {}

    void show() {
        cout << "各科成绩为：" << chi << "," << math << "," << eng << endl;
    }
};

class Student {
private:
    string name;
    int sno;
public:
    Student(string n, int s) : name(n), sno(s) {}

    Student() {}

    void show() {
        cout << "姓名：" << name << "学号：" << sno;
    }

};

class UniversityStu : public Student {
private:
    string dept;//系
    Score score;//创建对象成员
public:
    //定义构造函数
    //父类狗在函数参数列表，对象成员构造函数参数列表，子类参数列表
    UniversityStu(string name, int no,unsigned c,unsigned m,unsigned e, string dept)
    : Student(name, no),score(c,m,e), dept(dept) {

    }

    UniversityStu() {}

    //定义函数show，输出大学生所有信息
    void show() {
        Student::show();
        cout << "所在系：" << dept << endl;
    }

};


int main() {
    UniversityStu universityStu("胡桃",1,88,66,65,"计算机");
    universityStu.show();
}

```



#### 带默认值的构造函数

```c++
#include "iostream"

using namespace std;

class Vehicle{//机动车
private:
    int wheel;//轮胎数量
    string brand;//品牌
public:
    //定义构造函数
    Vehicle(int wheel,string brand):wheel(wheel),brand(brand){}
    Vehicle(){}
    //自定义函数show，输出信息
    void show (){
        cout<<"轮胎数量："<<wheel<<"品牌："<<brand;
    }
};
//定义子类Car
//属性：passenger_load 载客人数
//构造函数的定义
//自定义函数show，输出信息
class Car:public Vehicle{
private:
    int passenger_load;
    Vehicle vehicle;
    //构造函数冒号后面可以有默认值，无顺序，默认值随意，最终取默认值
    //此时，冒号左侧对应的参数省略
public:
//    Car(int wheel,string brand,int passenger_load):vehicle(wheel,brand),passenger_load(passenger_load){}
    Car(int wheel,string brand,int passenger_load):vehicle(4,brand),passenger_load(passenger_load){}
    Car(){}
    void show(){
        vehicle.show();
        cout<<"，载客人数："<<passenger_load;
    }
};



int main() {
    //创建对象，输出车辆所有信息
    Car car(4,"璃月科技",4);
    car.show();
}
```



### 多继承

2024年5月6日

```c++
#include "iostream"

using namespace std;

class Teacher {
protected://本类及后代
    string name;
    string title;//职称
public:
    Teacher(string name, string title) : name(name), title(title) {}

    Teacher() {}

};

class Student {
protected://本类及后代
    string name;
    int sno;
public:
    Student(string name, int sno) : name(name), sno(sno) {}

    Student() {}

};

class Postgraduate : public Teacher, public Student {//多继承
private:
    double salary;
public:
    Postgraduate() {}

    //构造函数(参数):父类1(参数),父类2(参数)...

    Postgraduate(string name, string title, int sno, double salary) : Teacher(name, title), Student(name, sno),
                                                                      salary(salary) {}

    void show() {
        cout << "姓名:" << Teacher::name << ",职务:" << title << ",学号" << sno << ",工资:" << salary << endl;
        //当多个父类有同名属性时，需要添加作用域，避免二义性
    }
};

int main() {
    Postgraduate postgraduate("钟离","语文",101,0);
    postgraduate.show();
}
```

```c++
#include "iostream"

using namespace std;

class Sofa {
protected:
    string color;
    string brand;//品牌
public:
    void setColorBrand(string c,string b){
        color = c;
        brand = b;
    }

    Sofa() {}

    void show() {
        cout << "芝士沙发" << endl;
    }
};

class Bed {
protected:
    string color;
    string brand;
public:
    void setColorBrand(string c,string b){
        color = c;
        brand = b;
    }

    Bed() {}

    void show() {
        cout << "(～﹃～)~zZ" << endl;
    }
};

class SofaBed : public Sofa, public Bed {//多继承
private:
    double price;
public:
    SofaBed(double price):price(price){}

    void display(){
        cout<<"品牌:"<<Sofa::brand<<endl;
        cout<<"颜色:"<<Sofa::color<<endl;
        cout<<"价格:"<<price<<endl;
        Sofa::show();//加作用域
        Bed::show();
    }
};

int main() {
    SofaBed sofaBed(100);
    sofaBed.Sofa::setColorBrand("绿色","沉歌壶");
    sofaBed.display();
}
```



### 虚基类

2024年5月10日

- 创建一个对象时，虚基类的构造函数优先于普通父类执行
- 虚基类构造函数只执行一次
- 先执行虚基类构造函数，再执行普通父类的构造函数，再执行本类的构造函数



```c++
#include "iostream"

using namespace std;

class A{
public:
    A(){
        cout<<"A"<<endl;
    }
};


class B{
public:
    B(){
        cout<<"B"<<endl;
    }
};

class C:public B,public virtual A{
public:
    C(){
        cout<<"C"<<endl;
    }
};

class D:public B,public virtual A{
public:
    D(){
        cout<<"D"<<endl;
    }
};

class E:public C,public virtual D{
public:
    E(){
        cout<<"E"<<endl;
    }
};

int main(){
    A a;//A
    B b;//B
    C c;//ABC
    D d;//ABDBCF
    E e;//ABCBDF
}
```



### 类模板

类模板为类定义一种模式，使得类中的某些数据成员、某些成员的参数、某些成员函数的返回值，能取任意类型

模板类

C++语言编译系统根据类模板和特定的数据类型来产生一个类，即模板类

对象是类的实例

模板类是类模板的实例

类是对象的模板



## 第六章 多态性和虚函数

运算符重载赋予运算符多重含义



**三种多态实现方式**

- 函数重载
- 运算符重载
- 虚函数

运算符重载实质是**函数重载**

**五类运算符**

- 类属关系运算符  **.**
- 成员指针运算符  **.***
- 作用域运算符  **::**
- 测试运算符  **sizeof**
- 三目运算符  **?:**

双目运算符默认只有**一个参数**，为**右侧**，左侧默认**被this引用**

前置运算符**没有参数**

后置单目运算符重载为类成员函数参数有**1个，整形**





对象进行操作



### 运算符重载

2024年5月13日

```c++
#include "iostream"

using namespace std;

class Complex {//复数类
private:
    double real, imag;//实数，虚数
public:
    //构造函数初始化数据成员
    Complex(double real, double imag) : real(real), imag(imag) {}

    Complex() {}//定义无参构造函数
    //把+运算符重载为类的成员函数
    Complex operator+(Complex complex) {
        Complex complex_num;//两个复数加法后的新的复数
        complex_num.real = this->real + complex.real;//两个复数实数部分相加
        //this->real：第一个对象的实数部分
        complex_num.imag = this->imag + complex.imag;//两个复数虚数部分相加
        return complex_num;
    }
    Complex operator-(Complex complex) {
        Complex complex_num;//两个复数减法后的新的复数
        complex_num.real = this->real - complex.real;//两个复数实数部分相加
        //this->real：第一个对象的实数部分
        complex_num.imag = this->imag - complex.imag;//两个复数虚数部分相加
        return complex_num;
    }

    void show() {//输出复数
        cout << "(" << real << "," << imag << ")" << endl;
    }
};

int main() {
    Complex c1(3, 5), c2(5, 8), c3, c4;
    c1.show();
    c2.show();
    c3 = c1 + c2;//当两个对象进行+运算时，系统会自动调用+运算符重载函数
    c3.show();
    c4 = c1 - c2;
    c4.show();
}
```

```c++
//
// Created by 26371 on 24-5-13.
//运算符重载2
#include "iostream"
#include <windows.h>

using namespace std;

class Time {
private:
    int hour, minute, second;
public:
    Time(int h, int m, int s) : hour(h), minute(m), second(s) {}

    Time() {}

    Time operator++() {//定义前置单目运算符++重载函数（重载不变）
        second++;
        if (second == 60) {
            minute++;
            second = 0;
            if (minute == 60) {
                hour++;
                minute = 0;
                if(hour==13){
                    hour = 1;
                }
            }
        }
        return *this;//取到地址中的值
    }

    Time operator++(int) {//定义后置单目运算符++重载函数（重载不变）
        //加一个整形类型参数，形参可以省略
      Time old = *this;
      ++(*this);
      return old;
    }

    void show(){
        cout<<hour<<":"<<minute<<":"<<second<<endl;
    }


};

int main() {
    Time t(12,59,45);
//    while (true){
//        Sleep(1000);
    (++t).show();//当++对象名时，系统会自动调用前置运算符
    (t++).show();
//        (t.operator++()).show()等同于上方语句
//    }

}
```

```c++
//
// Created by 26371 on 24-5-17.
//运算符重载3
#include "iostream"

using namespace std;

class Test {
private:
    int data;//数值
public:
    Test(int data) : data(data) {}//构造函数初始化数据成员
    //把*运算符重载为类的成员函数，参数可以是普通对象的引用
    Test() {}

    Test operator*(Test &t1) {
        Test res;//接收两个对象数值乘积的结果
        res.data = this->data * t1.data;//两个对象值的成绩
        //this->data:第一个对象（操作数）的值，此处可省略this
        return res;
    }

    Test operator/(Test &t1) {
        Test res;
        res.data = this->data / t1.data;
        return res;
    }

    Test operator%(Test &t1) {
        Test res;
        res.data = this->data % t1.data;
        return res;
    }

    void show() {
        cout << data << endl;
    }
};

int main() {
    Test t1(17), t2(8), t3;
//    t3=t1*t2;当两个对象进行乘法运算时，系统会自动调用*运算符重载函数
    t3 = t1.operator*(t2);
    t3.show();

    t3 = t1.operator/(t2);
    t3.show();

    t3 = t1.operator%(t2);

    t3.show();
}
```

```c++
//
// Created by 26371 on 24-5-17.
//运算符重载4
#include "iostream"

using namespace std;

class Test {
private:
    int data;//数值
public:
    Test(int data) : data(data) {}//构造函数初始化数据成员
    //把*运算符重载为类的成员函数，参数可以是普通对象的引用
    Test() {}

    //友元函数内不存在this指针，所以参数要有两个
    friend Test operator*(Test &t1, Test &t2);//友元函数类内声明

    friend Test operator/(Test &t1, Test &t2);

    friend Test operator%(Test &t1, Test &t2);

    void show() {
        cout << data << endl;
    }
};

Test operator*(Test &t1, Test &t2) {
    Test res;//接收两个对象数值乘积的结果
    res.data = t1.data * t2.data;//两个对象值的成绩
    return res;
}

Test operator/(Test &t1, Test &t2) {
    Test res;
    res.data = t1.data / t2.data;
    return res;
}

Test operator%(Test &t1, Test &t2) {
    Test res;
    res.data = t1.data % t2.data;
    return res;
}

int main() {
    Test t1(17), t2(8), t3;
//    t3=t1*t2;当两个对象进行乘法运算时，系统会自动调用*运算符重载函数
    t3 = operator*(t1,t2);
    t3.show();
    t3 = operator/(t1,t2);
    t3.show();
    t3 = operator%(t1,t2);
    t3.show();
}
```

### 虚函数

虚函数定义

虚函数的目的是为了实现子孙的重写，目的是实现多态性

```c++
//
// Created by 26371 on 24-5-17.
//虚函数1
#include"iostream"

using namespace std;

class Animal {
public:
    virtual void eat() {
        cout << "库库炫" << endl;
    }

    virtual void cry() {
        cout << "嗷嗷哭" << endl;
    }

    void sleep() {
        cout << "overzzz" << endl;
    }
};

class Cat : public Animal {
public:
    void eat() {
        cout << "库库炫鱼" << endl;
    }

    void cry() {
        cout << "喵喵喵" << endl;
    }

    void sleep() {
        cout << "喵z喵z喵z" << endl;
    }
};

class Dog : public Animal {
public:
    void eat() {
        cout << "库库炫肉" << endl;
    }

    void cry() {
        cout << "汪汪汪" << endl;
    }
};

int main() {
    Animal a;//创建父类对象
    a.eat();
    a.cry();//调用父类自己的函数

    Cat c;//创建子类对象
    c.eat();
    c.cry();//调用子类自己的函数

    Dog d;
    d.eat();
    d.cry();

    Animal *t;//创建指向对象的指针变量，即只针对想
    t->eat();
    t = &a;

    t = &c;//把子类对象赋值给父类，t（可以理解为上转型对象）可以调用子类中重写或继承的成员，但不能子类新增加的成员
    t->eat();//调用子类cat中重写的函数
    t->f();//调用子类cat继承的函数
    t=&d();
    t->cry();//调用子类dog中重写的函数

    Animal *s = new Animal;//创建只只针对象
    s->cry();
    s->eat();

    s = new Dog;//把子类对象赋值给父类

    s= new Cat;//把子类赋值给父类

    //父类中方法若想被子类重写，必须在父类函数中加virtual（虚函数）
    //子类重写父类函数时，默认时虚函数，可省略virtual，建议显示的写出virtual
}
```



### 纯虚函数和抽象类

纯虚函数是一种特殊的虚函数，在声明”初始化“时为0的函数，



- 纯虚函数没有函数体
- 纯虚函数什么语句最后面的
- 纯虚函数声明语句最后应有分号
- 纯虚函数只有函数的名字，没有功能，不能被调用，将在派生类定义
- 多态性
- 继承过来的虚函数还是虚函数
- 只有类中才能声明纯虚函数



```c++
/*
大连交通大学
2024-05-20 11:28
author:马延旭
title:纯虚函数1
*/
#include "iostream"

using namespace std;

const double PI = 3.14; // 常量
class Point             // 包含纯虚函数的累成为抽象类
{
protected:
    int x, y;

public:
    Point(int a, int b) : x(a), y(b) {}
    Point() {}

    virtual double getArea() = 0; // 纯虚函数，

    virtual void show() = 0; // 纯虚函数，显示信息
};

class Circle : public Point
{
protected:
    double r;

public:
    Circle(int a, int b, double ra) : Point(a, b), r(ra) {}
    virtual double getAtea() // 重写父类方法
    {
        return PI * r * r; // PI*pow(r,2)
    };
    virtual void show()
    {
        cout << "圆心坐标:(" << x << "," << y << ")" << endl;
        cout << "圆的面积：" << getArea() << endl;
    }
};

class Cylinder : public Circle
{
private:
    double h;

public:
    Cylinder(int a, int b, double ra, double h) : Circle(a, b, ra), h(h) {}
    virtual double getArea()
    { // 重写父类Circel方法
        return 2 * PI * r * h;
    }
    double getVolume()
    {                                 // 柱体体积
        return Circle::getArea() * h; // 以圆为底
    }
    virtual void show()
    {
        cout << "圆柱侧面积:(" << getArea() << ")" << endl;
        cout << "圆柱体体积：" << getVolume() << endl;
    }
};

int main()
{
    // Point p;错误，不能对抽象类创建对象，不能实例化抽象类
    //Point *p = new Circle(3, 6, 2.5); // 把子类创建对象的引用赋值给父类指针
    Point *p;
    p->show();

    p = new Cylinder(1, 2, 3, 4);
    p->show();
}

```

```c++
/*
大连交通大学
2024-05-20 11:15
author:马延旭
title:虚函数2
*/
#include <iostream>

using namespace std;

class Animal
{
public:
    // 定义纯虚函数
    virtual void cry() = 0;
    virtual void eat() = 0;
};

class Cat : public Animal
{
public:
    virtual void cry()
    {
        cout << "喵喵喵" << endl;
    }
    virtual void eat()
    {
        cout << "炫鱼" << endl;
    }
};

class Dog : public Animal
{
public:
    virtual void cry()
    {
        cout << "汪汪汪" << endl;
    }
    virtual void eat()
    {
        cout << "炫肉" << endl;
    }
};

void f1(Animal *t)//参数是抽象类的指针变量
//根据不同实体调用相应重写的方法
{
    t->cry();
    t->eat();
}

void f2(Animal &a)//参数是抽象类的对象的引用
//根据不同实体调用相应重写的方法
{
    a.cry();
    a.eat();
}
int main()
{
    Cat c;
    Dog d;
    f1(&c);//调用方法f1，传参是对象的地址
    f2(c);//调用方法f2，传参是对象

    f1(&d);
    f2(d);
    return 0;
}

/*
 * 虚函数实现多态性：
 * 满足的条件
 * 1.一定是在继承的环境中
 * 2.子类重写父类虚函数
 * 实现是方式
 * 1.用父类的指针变量或对象的引用去调用子类重写的方法
 */
```





#### 抽象类

凡是包含纯虚函数的类都是抽象类

如果在子类中，没有重写所有父类中的抽象类，子类也还是抽象类

如果全部实现，子类不算抽象类

抽象类无法实例化，但是可以定义指针变量，通过指针调用子类，实现多态性能



### 虚析构函数

构造函数不能构造成虚函数

对析构函数构造成虚函数

如果一类的**析构函数**是**虚函数**的话，继承他的派生类，**所以子类**的**析构函数**都是**虚函数**

析构函数设置为虚函数后，使用**指针**引用可以**动态绑定**

作用：使用基类类型的指针能够调用适当的虚构函数释放不同对象的内存

**无故声明虚析构函数**和**永远不声明虚析构函数**都是**错误**的

父类中如果定义了一个虚函数的情况下，建议子类定义虚析构函数

由于使用了虚析构函数实现了多态性，使得子类的析构函数调用，子类对象申请的动态空间实现了释放

```c++
/*
大连交通大学
2024-05-24 08:27
author:马延旭
title:虚析构函数
*/
#include <iostream>

using namespace std;
//自底向上去释放空间

class Father {
public:
    virtual ~Father() {//定义虚析构函数（不能重载）
        cout << "father" << endl;
    }
};

class Son : public Father {
private:
    int *p;//定义整型类型指针变量
public:
    Son() {
//        p = new int;为指针申请空间，系统提供默认int型值
        p = new int(12);//为指针申请空间并初始化
    }

    ~Son() {
        cout << "son" << endl;
        delete p;//释放指针空间
    }
};

void test(Father *t) {//参数是父类的指针变量
    delete t;//释放空间，系统自动析构函数

};

int main() {
//    Father *s = new Son();//父类指针只想子类空间
//    test(s);
    Father f;
    Son s;//创建子类对象
    test(&s);//子类的地址

}
```



## 第七章 C++的流类库与输入输出

### 重载输入输出

系统提供istream与ostream，cin和cout分别是istream和ostream的对象

```c++
//
// Created by 26371 on 24-5-27.
//输入输出流运算符重载函数1
#include "iostream"

using namespace std;

class Point {
private:
    int x, y;
public:
    //输入流运算符>>重载为类的非成员函数（友元函数）
    friend istream &operator>>(istream &in, Point &p);

    //输出流运算符<<重载为类的非成员函数（友元函数）
    friend ostream &operator<<(ostream &out, Point &p);
};

//输入流运算符重载函数的实现
istream &operator>>(istream &in, Point &p) {
    in >> p.x >> p.y;//从键盘为对象x，y赋值
    return in;//返回输入流对象
}

//输出流运算符重载函数的实现
ostream &operator<<(ostream &out, Point &p) {
    out << "(" << p.x << "," << p.y << ")\n";//输出坐标
    return out;//返回输出流对象
}


int main() {
    Point p1, p2;
    cout<<"请输入第一个对象的坐标：\n";
    cin>>p1;//当>>后面连接对象名时系统自动调用
    //输入流运算符重载函数
    cout<<"p1="<<p1;//当<<后面链接对象名时系统自动调用
    //自动调用输出流运算符重载函数


}
```

### 文件的输入输出

P266

filename：指要打开的文件

mode：指打开文件的方式

access：指打开文件的属性

发开文件的方式在类ios中定义，常用值如下

ios:in文件输入方式打开（文件数据输入到内存）

ios:out文件输出方式打开（内存数据输入到文件）

0是默认值

1是只读文件

2是隐含文件

4是系统文件

#### 文件的读取

从文件读取时，若文件不存在，会出错，需要事先创建文件

```c++
//
// Created by 26371 on 24-5-27.
//文件的读取
#include "iostream"
#include "fstream"//加载头文件
using namespace std;
void readFile(){
    //2-创建读取文件流对象
    ifstream ifs;//fstream子类
    //3-打开文件（判断是否成功打开）
    ifs.open("../data.txt",ios::in);
    if (ifs.is_open()){
        cout<<"打开文件成功"<<endl;
    }else{
        cout<<"打开文件失败"<<endl;
    }
    //4-读取文件内容（有四种方法）
    //1.单个字符读取，存放到字符数组中
    char a[1024];
    while (ifs>>a){//读一个字符，存入a数组中
        cout<<a<<endl;//不会自动换行，把空格及回车符当分隔符，才换行
    }
    
    //2.按行读取，存档在字符数据中
    char a[200];
    while (ifs.getline(a,200)){//参数：存档到数组中，读取个数
        cout<<a<<endl;//不会自动换行需要手动换行
    }
    
    //3.按单个字符读取，用get方法读取，一次读取一个字符
    char c;
    while ((c = ifs.get()) != EOF) {//EOF：end of file到达文件末尾
        cout << c;//会自动换行
    }
    
    //4.按行读取，存放在字符串中
    string s;
    while(getline(ifs,s)){//参数：from(文件来源)，to(存到哪里)
        cout<<s<<endl;//不会自动换行，需要手动换行
    }

    //5-关闭文件流对象
};

//自定义函数用于读取文件
int main(){
    readFile();
}
```

乱码解决：更改保存文件的文件编码



#### 文件的写入

当文件写入数据时，若文件不存在，系统会自动创建

```c++
//
// Created by 26371 on 24-5-31.
//文件的写入
#include "iostream"
#include "fstream"//1-记载头文件

using namespace std;

void writeFile() {
//    2.创建文件写入流对象
    ofstream ofs;
//    3.打开文件
    ofs.open("data.txt", ios::out|ios::app);//参数：路径，打开方式“可写入”ios::app续写文件
//    4.写入数据
    ofs << "109,穹,67,女,17,535353453\n";
    ofs << "108,卡夫卡,90,女,90,534535\n";
    ofs << "107,温迪,30,男,79,353453\n";
    ofs << "106,神里凌华,60,女,26,45353453\n";
    ofs << "105,心海\t,100,女,28,535353\n";
    char a[] = "（￣︶￣）\n";
    string s = "(～﹃～)~zZ";

    ofs.write(a, sizeof(a));//将字符数组a整体写入文件

//    for (int i = 0; i < sizeof(a); ++i) {
//        ofs.put(a[i]);//把数组中每个字符写入到文件中
//    }
//    for (int i = 0; i < size(s); ++i) {
//        ofs.put(s[i]);
//    }

}

int main() {
    writeFile();
}
```



### 习题

1.头文件iostream中定义了4个标准流对象，分别是**cin**（标准输入流对象），**cout**（标准输出流对象），**cerr**（标准错误流对象），**clog**（标准日志流对象）。
2.用标准输入流对象cin与提取操作符>>连用进行输入时，可以使用**setf函数**来设置输入流的格式状态，并可以使用unsetf函数来取消某种格式状态。
3.每一个输入流对象都有一个**flags**成员函数来控制流的格式的方法。
4.C++提供了使用getline函数和get函数来读入数据；文件输出则可以使用put函数和putline函数来实现。
5.文件输入和文件输出都需要使用文件对象，通过open函数打开文件，通过close函数关闭文件。
6.文本文件是存储ASCII码字符的文件，文本文件的输入可以使用ifstream对象的getline函数和get函数来实现。文本文件的输出可以使用ofstream对象的put函数和putline函数来实现。在处理文本文件时，需要注意的是，文件的输入输出可能需要进行字符的转换，例如在Windows系统中，文件的换行符是"\r\n"，而在Unix系统中，文件的换行符是"\n"，如果在不同系统间传输文件，可能需要进行换行符的转换。



## 第八章 异常处理

程序错误有两种

- 编译错误
  - 语法错误
- 运行时错误
  - 不可预料的逻辑错误
  - 可以预测的运行异常



try throw catch

try后是可能产生错误的语句段

throw表达式是抛出异常

catch进行异常处理，捕获异常

一个try可以对应多个catch



### 重新抛出异常和异常规范

当catch捕获异常的时候，可能不能完全解决异常，将异常传递到更上级的函数进行处理









## 练习

### 矩形相等

输入两个矩形长宽，判断两个矩形是否面积相等

```c++
#include "iostream"

using namespace std;

class Rectangle {
private:
    double length, width;
public:
    Rectangle(double l, double w) : length(l), width(w) {}

    Rectangle() {}

    double Area() {
        return length * width;
    }

    friend bool isEqual(Rectangle &rectangle1, Rectangle &rectangle2);
};

bool isEqual(Rectangle &rectangle1, Rectangle &rectangle2) {
    return rectangle1.Area() == rectangle2.Area();
}


int main() {
    Rectangle rectangle1(3,6);
    Rectangle rectangle2(5,6);

    cout<<isEqual(rectangle1,rectangle2);
}
```





### 银行存取款

定义存款取款

```c++
#include "iostream"

using namespace std;

class BankAccount {
private:
    int balance;
public:
    BankAccount(int b) : balance(b) {}

    BankAccount() {}

    friend int deposit(BankAccount &bankAccount, int num);//存款
    friend int withdraw(BankAccount &bankAccount, int num);//取款
};

int deposit(BankAccount &bankAccount, int num) {
    return bankAccount.balance + num;

}

int withdraw(BankAccount &bankAccount, int num) {
    if (num > bankAccount.balance) {
        cout<<"余额不足";
        return num;
    } else {
        return bankAccount.balance - num;
    }
}

int main() {
    int balance;
    cout << "您的账户余额：";
    cin >> balance;
    BankAccount bankAccount = BankAccount(balance);
    cout << "存款：";
    cin >> balance;
    cout << deposit(bankAccount, balance) << endl;
    cout << "取款：";
    cin >> balance;
    cout << withdraw(bankAccount, balance);

}
```



### 计算坐标系两点坐标距离

两点坐标，计算两点之间距离

```c++
#include <valarray>
#include "iostream"

using namespace std;
int diff(int num1, int num2);

class Point{
private:
    int x,y;
public:
    Point(int x,int y):x(x),y(y){}
    Point(){}

    friend double distance(Point &p1,Point &p2);
};

double distance(Point &p1,Point &p2){
    int xlength,ylength;
    xlength = diff(p1.x,p2.x);
    ylength = diff(p1.y,p2.y);
    return sqrt(pow(xlength,2)+pow(ylength,2));
}

int diff(int num1, int num2) {
    if (num1 > num2) {
        return num1 - num2;
    } else {
        return num2 - num1;
    }
}

int main() {
    int x,y;

    cout<<"输入第一个点坐标(x,y)：";
    cin>>x>>y;
    Point point1 = Point(x,y);
    cout<<"输入第二个点坐标(x,y)：";
    cin>>x>>y;
    Point point2 = Point(x,y);

    cout<<"两点距离为："<<distance(point1,point2);
}

```

### 虚函数练习

创建一个基类Person，包含属性name和age，以及一个虚函数displayInfo()用于显示个人信息。从Person类派生出Student和Teacher类，分别添加额外的属性（如学生的学号和老师的职称），并重写dislayInfo()函数以显示学生和老师的信息。

```c++
#include<iostream>

using namespace std;

class Person {
protected:
    string name;
    int age;

public:

    Person(string name, int age) {
        this->name = name;
        this->age = age;
    }

    virtual void displayInfo() {
        cout << "姓名:" << name << ", 年龄:" << age << endl;
    }
};

class Student : public Person {
public:
    int id;

    Student(string name, int age, int id) : Person(name, age), id(id) {}

    virtual void displayInfo() {
        cout << "姓名:" << name << ", 年龄:" << age << ", 学号:" << id << endl;
    }
};

class Teacher : public Person {
protected:
    string title;
public:

    Teacher(string name, int age, string title) : Person(name, age), title(title) {}

    virtual void displayInfo() {
        cout << "姓名:" << name << ", 年龄:" << age << ", 职称:" << title << endl;
    }
};

int main() {
    Person p("一月", 30);
    p.displayInfo();

    Student s("二月", 20, 100);
    s.displayInfo();

    Teacher t("三月", 35, "C++老师");
    t.displayInfo();

    Student d("一月",20,1);
    s.displayInfo();

    Person *f = new Student("二月",22,2);
    f->displayInfo();

}
```





