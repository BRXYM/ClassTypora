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



### 变量

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



### 类型转换

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



### 内存空间的申请和释放

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



### 内联函数

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



### 参数带默认值的函数

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



### 函数重载

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



### 函数模板

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

### 创建类与对象

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

### this指针的使用

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



### 内联函数和构造函数

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



### 外联函数

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



### 格式化

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
    //用fixed与setprecision(n)联用:n表示小数部分保留的位数

    cout << setw(5) << x;
    cout << setw(5) << y << endl;
    //setw(n)总共占n位,不够默认空格补齐,默认右对齐

    cout << setiosflags(ios::left) << setw(5) << x;
    cout << setiosflags(ios::left) << setw(5) << y << endl;
}
```



### 对象数组

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



### 对象数组键盘赋值

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



### 数据成员初始化

#### 构造函数初始化方式一

```c++
Animal(string name, string type, int age) {
    this->name = name;
    this->type = type;
    this->age = age;
}
```

#### 构造函数初始化方法二

```c++
Animal(string n,string t,int a):name(n),type(t),age(a){}
```

#### 构造函数初始化方法三

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
   

### 含有对象成员的构造函数及析构函数

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



### 指针变量

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

**友元的分类**

1. 友元函数
2. 友元成员
3. 友元类

### 友元的定义

声明友元函数，在**类内声明**，**类外实现**方法体

**优点**

- 友元函数并不属于类中成员，它可以访问类中所有所有成员，(重点是private和protected)
- 能够提高程序的运行效率，可以使类与类之间合作共同完成某一任务
- 友元函数一般参数是对象的调用，通过引用类中成员

**缺点**

- 破坏了类的封装性和隐蔽性，尽量少用

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

