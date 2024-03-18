# **Java**

## Java的版本

- **JavaSE（J2SE）**
- **JavaEE（J2EE）**
- JavaME（J2ME）



## Java语言的特点

- Java是**面向对象**的语言。
- Java是分布式语言。
- Java是健壮的。
- Java是**安全**的。
- Java是中立性结构。
- Java是高效能的程序。
- Java支持多线程。



## JDK、JRE、JVM的关系(*)

- JDK：可以**开发、编译与运行**Java应用程序与小应用程序的工具。
- JRE：可以**运行**Java应用程序与小应用程序的工具。
- JVM：**Java虚拟机**。是Java实现**跨平台**最重要的工具。可以运行字节码文件。



## JDK的安装与配置

- 安装/解压JDK时，尽量放在**非中文目录**中。

- JDK的目录结构

  - bin目录：保存与Java相关的应用程序。
  - conf目录：保存Java配置。

- **配置环境变量：**

  - 此电脑-->右键-->属性-->高级系统设置

    <img src="D:\华信教育\2023下\Java\images\9-10\image-20230918090019804.png" alt="image-20230918090019804" style="zoom:80%;" />

  - 系统变量

    - path：只能编译，不能新建。JDK的bin目录。

      <img src="D:\华信教育\2023下\Java\images\9-10\image-20230918090726762.png" alt="image-20230918090726762" style="zoom:80%;" />

    - JAVA_HOME：JDK的路径。

      <img src="D:\华信教育\2023下\Java\images\9-10\image-20230918091524192.png" alt="image-20230918091524192" style="zoom:80%;" />

    - classpath：一个点。

      <img src="D:\华信教育\2023下\Java\images\9-10\image-20230918091823425.png" alt="image-20230918091823425" style="zoom:80%;" />

    - cmd-->java -version



## 编写Java代码注意事项

- Java代码**区分大小写**。
- 大部分Java代码使用**分号**表示结束。
- Java代码中只能直接使用**英文**标点符号。



## 第一个Java示例

- 示例代码

  ```java
  public class Test{
      public static void main(String[] args) {
          System.out.println("第一个Java示例");
      }
  }
  
  class A{
  }
  
  class B{
  }
  ```

- 通常情况下，Java代码需要放在**类**(class)中。

- main()方法是程序的**入口**。

- **main()方法的格式不能改变**。

- **一个.java文件中可以出现多个类**。

- **一个.java文件中只能出现一个公有(public)的类**。

- **公有类的名字必须与文件名字保持一致(包含大小写)**。

- **main()方法不需要必须放在公有的类中**。



## javac与java命令

- javac命令：首先**检查**Java代码是否存在**语法错误**。如果存在语法错误，则提示相关的异常信息。如果不存在语法错误，则**根据.java文件编译生成.class文件**。
- java命令：**运行.class文件**。



## Java的文件类型(*)

- **.java文件：源文件。用于保存Java源代码，文本文件。**
- **.class文件：类文件。用于保存字节码，二进制文件。**



## Java命名规范

- **类名：首字母大写，其它字母均为小写。如果类名由多个单词组成，每个单词首字母大写，其它字母均为小写。如：User、EmployeeService。**
- **变量名：所有字母均为小写。如果变量名由多个单词组成，则从第二个单词开始每个单词首字母大写，其它字母均为小写。如：name，userAge。**
- **方法名：所有字母均为小写。如果方法名由多个单词组成，则从第二个单词开始每个单词首字母大写，其它字母均为小写。如：equals()，setUserName()，getUserAge()**。
- **包名：所有字母均为小写。如：org.springframework.boot、com.mysql.cj.driver。**
- **使用static final修饰的常量：所有字母均为大写。如果由多个单词组成，单词之间使用下划线分隔。如：MAX_VALUE、RED**。
- **泛型名：只有一个大写字母。如：K、V、E**。



## Eclipse常用快捷键

- 生成main()方法：main + Alt + /，回车。
- 生成System.**out**.println()：syso + Alt + /，回车。
- 运行：Ctrl + F11
- 调试：F11
- 添加/取消单行注释：选中内容，Ctrl + /。
- 添加多行注释：Ctrl + Shift + /
- 取消多选注释：Ctrl + Shift + \
- 整理代码格式：Ctrl + Shift +F。代码-->右键-->Source-->Format。
- 改变字体大小：Ctrl + 加号/减号。
- 批量修改变量名：选中需要改名的变量，Alt + Shift + R，输入新变量名，回车。



## Java基础

- Java只有**两种**数据类型：**基本数据类型、引用数据类型**。



### Java的基本数据类型

- Java有**八种**基本数据类型
- 整数类型：**Java中没有无符号的整数**。**Java中的整数默认为十进制，也可以表示八进制(用0开头)，也可以表示十六进制(用0X或0x开头)，也可以表示二进制(用0B或0b开头)**。
  - **byte**：1个字节，-2<sup>7</sup> -- 2<sup>7</sup> - 1。
  - **short**：2个字节，-2<sup>15</sup> -- 2<sup>15</sup> - 1。
  - **int**：4个字节，-2<sup>31</sup> -- 2<sup>31</sup> - 1。**Java中代码中直接出现的整数默认为int类型**。
  - **long**：8个字节，-2<sup>63</sup> -- 2<sup>63</sup> - 1。**在整数后面加L/l可以将int转换为long类型。**
- 浮点类型：**Java中浮点数的运算一定会产生误差**。
  - **float**：4个字节，单精度，**在浮点数后面加F/f可以将double转换为float类型**。
  - **double**：8个字节，双精度，**Java代码中直接出现的浮点数默认为double类型**。
- 字符类型：**char**。**字符类型的值必须出现在一对单引号中，并且通常情况下，单引号中只能出现一个字符**。Java使用**Unicode**字符集，**Unicode字符集中所有的字符均为两个字节**。
- 布尔类型：**boolean**，**只有两个值：true/false。Java中boolean类型不能转换为其它数据类型**。



### Java中标识符命名规则(*)

- Java中标识符由**字母、数字、下划线、美元符**组成。
- 标识符**不能使用数字开头**。
- 标识符**不能使用关键字**（Java中关键字均为小写）。
- **Java中有三个特殊的值：true、false、null。不能作为标识符**。
- 中文也可以作为标识符。



### 变量与常量

- 变量

- 格式：数据类型 变量名 [= 值];

- **当变量没有赋值时，不能使用，否则编译失败。**

- **同一个范围内，不能声明同名的变量。**

- Java是**强类型**的语言。

  ```java
  char c = 'A';
  System.out.println(c);
  
  // 将Unicode字符集中第97个位置的字符赋给变量c
  c = 97;
  System.out.println(c);
  
  // 将十六进制的整数指定的Unicode字符集中指定位置的字符赋给变量c
  c = 0X100;
  System.out.println(c);
  
  // \u表示Unicode字符，\u + 4位十六进制整数
  c = '\u0036';
  System.out.println(c);
  ```

- 常量

- 格式：**final** 数据类型 常量名 [= 值];

- **常量只能赋值一次**。

  ```java
  final int age;
  age = 20;
  System.out.println(age);
  
  // age = 25; 错误，常量只能赋值一次
  System.out.println(age);
  ```



### 基本数据类型的类型转换

- 如何判断基本数据类型的大小：

  - 先判断基本数据类型的**精度**，精度大的基本数据类型大。
  - 当精度相同时，**字节**数大的基本数据类型大。

- **小**类型可以**直接转换**为**大**类型。

- **大**类型必须**强制转换**(强转)才能赋给**小**类型。

- **boolean不能转换为其它数据类型**。

- 当**值**(不是变量)在类型的取值范围内时，JVM会自动将值转换为对应的数据类型。

  ```java
  int x = 100;
  double y = x; // 小类型可以直接转换为大类型
  System.out.println(y);
  
  float f = (float) y; // 大类型必须强制转换才能赋给小类型
  System.out.println(f);
  
  
  byte b = 100; // 正确，当值(不是变量)在类型的取值范围内时，JVM会自动将值转换为对应的数据类型。
  System.out.println(b);
  
  // b = x; 错误，大类型必须强转才能赋给小类型
  System.out.println(b);
  ```

  

### 注释

- 注释是代码中不参与编译与运行的内容。

- 单行注释：// 注释内容
- 多行注释：/* 注释内容 */
- 文档注释：/** 注释内容 */，可以声明项目的帮助文档。



### 运算符

#### 算术运算符

- +、-、*、/、%、++、--

- **算术运算结果的类型**

  - 当参与算术运算的元素类型相同时，算术运算结果的类型一定与参与运算元素的类型保持一致。

  - 当参与算术运算的元素类型不同时，算术运算结果的类型一定与类型大元素类型相同。

  - **byte、short、char进行算术运算时，结果自动转换为int类型**。

    ```java
    int num1 = 5;
    int num2 = 2;
    System.out.println(num1 / num2); // 结果：2
    
    int num3 = 5;
    double num4 = 2.0;
    System.out.println(num3 / num4); // 结果：2.5
    
    char c1 = '1';
    char c2 = '2';
    System.out.println(c1 + c2); // 结果：99
    ```

  - **short s = 1; s = s + 1;是否存在错误？为什么？(*)**

    ```java
    short s = 1;
    // 错误，1是int类型，s是short类型，s+1的结果为int类型，int类型不能直接赋给short
    s = s + 1;
    ```

  - **不使用第三个变量，交换两个整型变量的值**(*)

    ```java
    // 借助第三个变量，交换两个整型变量的值
    int x = 100;
    int y = 200;
    int z = x;
    x = y;
    y = z;
    
    System.out.println(x);
    System.out.println(y);
    
    // 不借助第三个变量，交换两个整型变量的值
    int a = 1000;
    int b = 2000;
    a = a + b;
    b = a - b;
    a = a - b;
    System.out.println(a);
    System.out.println(b);
    ```

- ++、--

  - ++、--可以出现在**变量**的前面/后面。

  - **无论++、--出现在变量的前面/后面，代码"执行后"变量一定会加/减1**。

    ```java
    int num = 100;
    ++num;
    System.out.println(num);
    
    num++;
    System.out.println(num);
    ```

  - **++、--出现在变量的前面/后面的区别？**

    - **++、--出现在变量的前面：先计算，再取值。**
    - **++、--出现在变量的后面：先取值，再计算。**

    ```java
    int x = 100;
    int y = ++x;
    // x = x + 1;
    // int y = x;
    System.out.println(y);
    
    y = x++;
    // y = x;
    // x = x + 1;
    System.out.println(y);
    ```

    ```java
    int num = 0;
    for(int i = 0 ; i < 10 ; i++) {
        // 当变量等于自身++/--时，++/--无效
        num = num++;
    }
    System.out.println(num); // 输出：0
    ```



#### 比较运算符(关系运算符)

- &gt;、>=、&lt;、<=、==、!=
- **比较运算结果的类型一定为boolean类型**。
- **Java是否所有的数据类型都可以进行比较运算?请举例说明?(*)**
  - 不可以。
  - **Java中boolean类型不能与其它类型进行比较运算**。
  - 基本数据类型不能与引用数据类型进行**直接**的比较运算。



#### 逻辑运算符

​	<img src="D:\华信教育\2023下\Java\images\9-10\image-20230927144835290.png" alt="image-20230927144835290" style="zoom:60%;" />

- **逻辑运算结果的类型一定为boolean类型。**
- **逻辑与(&)/逻辑或(|)**(*)
  
  - **逻辑与：当第一个表达式为false时，仍然执行第二个表达式，再返回false。效率低，安全性差。**
  - **逻辑或：当第一个表达式为true时，仍然执行第二个表达式，再返回true。效率低，安全性差。**
  
- **短路与(&&)/短路或(||)**(*)

  - **短路与：当第一个表达式为false时，不执行第二个表达式，直接返回false。效率高，安全性好。**
  - **短路或：当第一个表达式为true时，不执行第二个表达式，直接返回true。效率高，安全性好。**

- 逻辑非(!)：取反。

  ```java
  String s = "admin";
  // 判断两个字符串是否相等
  System.out.println(s.equals("admin"));
  // 判断两个字符串是否不相等
  System.out.println(!s.equals("admin"));
  ```



#### 赋值运算符

- =、+=、-=、*=、/=、%=

- **short s = 1; s += 1;是否存在错误？为什么？**(*)

  ```java
  short s = 1;
  // 正确，+=、-=、*=、/=、%=会自动转换结果的类型
  s += 1;
  System.out.println(s);
  ```



#### 字符串连接符：+

- **当字符串与其它类型的数据进行连接时，JVM会自动将其它类型的数据转换为字符串后，再进行连接**。

  ```java
  System.out.println(1 + 2); // 输出：3
  System.out.println("1" + "2"); // 输出：12
  System.out.println("1" + 2); // 输出：12
  System.out.println(1 + "2"); // 输出：12
  ```




#### 三元运算符

- 格式：X ? Y : Z

- 当X为true时，返回Y。当X为false时，返回Z。

  ```java
  int age = 20;
  		
  System.out.println(age > 20 ? 100.00 : 1); // 输出：1.0
  ```

  

## 随机数

### Math.random()方法

- **random()：返回大于等于0.0，但一定小于1.0的double类型的随机数(*)**。

  ```java
  System.out.println(Math.random());
  // 返回1-100之间的随机整数
  System.out.println((int)(Math.random() * 100 + 1));
  // 返回随机小写字母
  System.out.println((char)(Math.random() * 26 + 'a'));
  // 返回随机大写字母
  System.out.println((char)(Math.random() * 26 + 'A'));
  ```

### java.util.Random类

- Random类：随机数生成器。

  ```java
  System.out.println(random.nextInt());
  System.out.println(random.nextDouble());
  // 返回大于等于0，但一定小于5的随机整数
  System.out.println(random.nextInt(5));
  // 返回大于等于1，但一定小于6的随机整数(JDK17开始出现)
  System.out.println(random.nextInt(1, 6));
  ```

  

## 输出与输入

### 输出

- **System.out.print()与System.out.println()的区别(*)？**
  - System.out.print()：输出数据不换行，方法必须有参数。
  - System.out.println()：输出数据并换行，方法可以没有参数。

### 输入：java.util.Scanner类

- 从JDK1.5开始出现，用于接收数据。

  ```java
  // 创建Scanner类型的变量，接收来自于键盘的数据
  Scanner sc = new Scanner(System.in);
  System.out.print("请输入编号：");
  // 等待用户在键盘中输入整数，以回车作为结束的标记
  int userId = sc.nextInt();
  
  System.out.print("请输入姓名：");
  // 等待用户在键盘中输入字符串，以回车作为结束的标记
  // next():用户输入的字符串中不能包含空格，如果出现空格，则空格与空格之后的内容无法获得
  String userName = sc.next();
  
  System.out.print("请输入工资：");
  // 等待用于在键盘中输入浮点数，以回车作为结束的标记
  double userSalary = sc.nextDouble();
  
  System.out.println("你的编号为：" + userId + ",你的姓名为：" + userName + ",你的工资为：" + userSalary);
  
  // 关闭流，使GC回收释放内存。
  sc.close();
  ```

  

## 分支选择

### if语句

- if语句的格式

  ```java
  if (条件) {
      // Java代码
  }
  
  Scanner sc = new Scanner(System.in);
  System.out.print("请输入一个整数：");
  int num = sc.nextInt();
  
  if (num % 2 == 0) {
      System.out.println(num + "是偶数");
  }
  
  if (num % 2 != 0) {
      System.out.println(num + "是奇数");
  }
  
  sc.close();
  
  if (条件) {
      // Java代码
  } else {
      // Java代码
  }
  
  Scanner sc = new Scanner(System.in);
  System.out.print("请输入一个整数：");
  int num = sc.nextInt();
  
  if (num % 2 == 0) {
      System.out.println(num + "是偶数");
  } else {
      System.out.println(num + "是奇数");
  }
  
  sc.close();
  
  // 接收用户在键盘中输入的成绩，并显示对应的等级
  Scanner sc = new Scanner(System.in);
  
  System.out.print("请输入你的成绩：");
  double num = sc.nextDouble();
  
  if (num >= 90) {
      System.out.println("优秀");
  } else if (num >= 80) {
      System.out.println("良好");
  } else if (num >= 70) {
      System.out.println("一般");
  } else if (num >= 60) {
      System.out.println("及格");
  } else {
      System.out.println("你挂了");
  }
  
  sc.close();
  ```

- **if语句条件结果的类型必须是boolean类型。**

- **if语句的大括号可以省略。如果省略则if语句的作用范围，只有一行Java代码。**

- **一个if语句中可以出现0个或1个else块。**

- **else块必须出现在if语句的最后。**

- **当if语句匹配到一个分支后，将不再匹配其它的分支，直接跳转到if语句的末尾。**

- **一个if语句中可以出现0个或N个else if块。**



### switch语句

- 格式与示例

  ```java
  switch(变量){
      case 值:
          // Java代码
          [break;]
      case 值:
          // Java代码
          [break;]
      ……
      default:
          // Java代码
  }
  
  import java.util.Scanner;
  
  public class TestSwitch {
  
  	public static void main(String[] args) {
  		// 接收用户输入的1-12之间的月份，并显示对应月份的天数
  		Scanner sc = new Scanner(System.in);
  
  		System.out.print("请输入1-12之间的月份：");
  		int month = sc.nextInt();
  		final int i = 2;
  
  		switch (month) {
  		case 1:
  		case 2 + 1:
  		case 5:
  		case 7:
  		case 8:
  		case 10:
  		case 12:
  			System.out.println(month + "月有31天");
  			break;
  		case 4:
  		case 6:
  		case 9:
  		case 11:
  			System.out.println(month + "月有30天");
  			break;
  		case i:
  			System.out.println(month + "月有28天");
  			break;
  		default:
  			System.out.println("月份不正确");
  		}
  		sc.close();
  	}
  }
  
  // 从JDK14开始出现的switch新语法，switch + Lamdba表达式，每个分支可以不写break。
  switch(变量) {
          case 值 -> {
              // Java代码
          }
          case 值 -> {
              // Java代码
          }
          ……
  }
  
  public class TestSwitch {
  
  	public static void main(String[] args) {
  		int num = 2;
  
  		switch (num) {
  		case 1 -> System.out.println("一");
  		case 2 -> System.out.println("二");
  		case 3 -> System.out.println("三");
  		case 4 -> System.out.println("四");
  		case 5 -> System.out.println("五");
  		case 6 -> System.out.println("六");
  		}
  	}
  }
  ```

- **switch中变量只能为byte,short,char,int。从JDK1.5开始可以使用枚举类型。从JDK1.8开始可以使用String类型**。

- **case后面的值不能重复。**

- **case后面的值只能为常量或字面值**。

- **case后面可以出现表达式，但表达式的结果不能与其它case后面的值重复。**

- **当switch匹配到一个分支后，会从此分支开始自顶向下执行所有的分支，直接switch的结束或遇到第一个break为止。**

- **default可以出现在switch语句的任意位置。**

- **无论default出现在哪，switch都会先匹配case分支。当switch没有匹配到任何case分支时，switch才会匹配default分支。**



## 循环结构

### while循环

- 格式

  ```java
  while (条件) {
      // 循环体
  }
  
  // 生成10个1-100之间的随机数
  int count = 1;
  
  while (count <= 10) {
      System.out.println((int)(Math.random() * 10 + 1));
      count++;
  }
  ```

- **当不确定循环次数时，建议使用while循环**。

- **while中条件结果的类型必须为boolean类型。**

- **while循环的大括号可以省略。如果省略，则while循环的作用范围为一行Java代码**。



### do..while循环

- 格式

  ```java
  do {
      // 循环体
  } while (条件);
  ```

- do..while循环的大括号不能省略。

- do..while循环必须使用分号表示结束。

- **while循环与do..while循环的区别?(*)**

  - while循环：先判断，再循环。
  - do..while循环：先循环，再判断。至少会循环一次。



### for循环

- 格式

  ```java
  for ([循环变量初始化];[循环条件];[循环变量的自增/自减]) {
      // 循环体
  }
  
  /*
  *第一次循环：先执行第一部分：i = 0。再执行第二部分：i < 4，返回true。进入循环，输出：0
  *第二次循环：先执行第三部分：i++,i = 1。再执行第二部分：i < 4，返回true。进入循环，输出：1
  *第三次循环：先执行第三部分：i++,i = 2。再执行第二部分：i < 4，返回true。进入循环，输出：2
  *第四次循环：先执行第三部分：i++,i = 3。再执行第二部分：i < 4，返回true。进入循环，输出：3
  *第五次循环：先执行第三部分：i++,i = 4。再执行第二部分：i < 4，返回false。循环结束
  */
  for(int i = 0 ; i < 4 ; i++) {
      System.out.println(i);
  }
  ```

- for循环括号中的三个部分都可以省略，但分号不能省略。

- **当确定循环次数时，建议使用for循环**。

- **for循环第一部分声明的变量属于循环的局部变量，只能在循环的内部使用。**

- for循环的第一部分可以声明多个**类型相同**的变量。

- **for循环第二部分结果的类型必须是boolean类型**。

- **for循环的大括号可以省略。如果省略，则for循环的作用范围只有一行Java代码。**



### break

- **break不能单独使用，只能出现在switch与循环语句中**。

- **break的作用：立即结束所在循环**。

  ```java
  for (int i = 1000; i <= 1100; i++) {
      if ((i % 3 == 2) && (i % 5 == 3) && (i % 7 == 2)) {
          System.out.println(i);
          break;
      }
  }
  ```

- 带标签的break

- **作用：立即结束标签后面的循环。**

  ```java
  loop: 
  for (int i = 0; i < 10; i++) {
      for (int j = 0; j < 10; j++) {
          System.out.print(i * j + "\t");
          if (j > i) {
              break loop;
          }
      }
      System.out.println();
  }
  ```



### continue

- **continue不能单独使用，只能出现在循环语句中**。

- **作用：使所在循环立即结束本次循环，直接进入下一次循环。**

  ```java
  for (int i = 1; i <= 100; i++) {
      if ((i % 3 != 0) || (i % 5 != 0)) {
          continue;
      }
      System.out.println(i);
  }
  ```

- 带标签的continue。

- **作用：使标签后面的循环立即结束本次循环，直接进入下一次循环**。

  ```java
  loop: 
  for (int i = 0; i < 10; i++) {
      for (int j = 0; j < 10; j++) {
          System.out.print(i * j + "\t");
          if (j > i) {
              continue loop;
          }
      }
      System.out.println();
  }
  ```

  

## 数组

- Java中的数组是一组**相同数据类型**的**集合**。
- **Java中的数组均为引用数据类型**。

### 一维数组

- 声明一维数组：**数据类型[] 数组名**;/数据类型 数组名[];。声明数组时会在**栈**内存中开辟**一个空间**保存数组的名字。**声明数组时不能指定数组的长度**。

- 创建一维数组：创建数组时在**堆**内存中开始**连续**的空间，用于保存数组的数据。**创建数组时必须指定数组的长度**。

  ```java
  // 创建数组并赋值
  int[] array = { 100, 200, 300 };
  // 创建指定长度的数组，但没有有数组中的元素赋值
  double array1[] = new double[10];
  // 通常用于重新为数组赋值
  String[] array2 = new String[] { "AA", "BB", "CC" };
  
  // 数组的长度可以为0，但此数组不能使用
  int[] array3 = new int[0];
  System.out.println(array3[0]);
  
  // 数组的长度不能为负数，否则运行时抛出异常
  String[] array4 = new String[-10];
  ```

  ![image-20231016084806234](D:\华信教育\2023下\Java\images\9-10\image-20231016084806234.png)

- **基本数据类型与引用数据类型的区别？(*)**
  
  - **基本数据类型栈内存中保存的是值。**
- **引用数据类型栈内存中保存的是引用。**
  
- 通过数组的**下标**可以**设置/获得**数组中的元素。下标格式：数组名[下标]。**数组的下标从0开始**。**数组最大的下标：数组长度 - 1**
- **java.lang.ArrayIndexOutOfBoundsException**：运行时异常，数组下标越界异常。
- 数组的长度：**length属性**。
- **数组的长度确定后就不能修改。**
- **数组的默认值：byte、short、int默认为0。long默认为0L。float默认为0.0F。double默认为0.0。char默认为'\u0000'。boolean默认为false。引用数据类型默认为null。(*)**

### 循环与数组

- 示例

  ```java
  public class TestArray {
  
  	public static void main(String[] args) {
  		int[] array = new int[10];
  		// 使用循环向数组中添加10个1-100之间的随机数
  		for (int i = 0; i < array.length; i++) {
  			array[i] = (int) (Math.random() * 100 + 1);
  		}
  
  		// 使用普通循环获得数组中所有的随机数
  		for (int i = 0; i < array.length; i++) {
  			System.out.print(array[i] + "\t");
  		}
  
  		System.out.println();
  		// forEach循环：从JDK1.5开始出现，用于遍历集合。
  		// forEach循环可以简化代码
  		// 通常用于从集合中获取数据
  		for (int i : array) {
  			System.out.print(i + "\t");
  		}
  	}
  }
  ```

### java.util.Arrays类

- Arrays类：与数组相关的工具类。

  ```java
  import java.util.Arrays;
  
  public class TestArray {
  
  	public static void main(String[] args) {
  		int[] array = new int[10];
  		// 使用循环向数组中添加10个1-100之间的随机数
  		for (int i = 0; i < array.length; i++) {
  			array[i] = (int) (Math.random() * 100 + 1);
  		}
  
  		// 使用普通循环获得数组中所有的随机数
  		for (int i = 0; i < array.length; i++) {
  			System.out.print(array[i] + "\t");
  		}
  
  		// Arrays类对数据进行升序排序
  		Arrays.sort(array);
  
  		System.out.println();
  		// forEach循环：从JDK1.5开始出现，用于遍历集合。
  		// forEach循环可以简化代码
  		// 通常用于从集合中获取数据
  		for (int i : array) {
  			System.out.print(i + "\t");
  		}
  
  		System.out.println();
  		// 倒序输出数组
  		for (int i = array.length - 1; i >= 0; i--) {
  			System.out.print(array[i] + "\t");
  		}
  	}
  }
  
  ```




## 类与对象

### 类中的成员变量(属性、字段、全局变量、域)

- 成员变量的作用：**用于描述类的特征**(*)。

- **new关键字的作用：在堆内存中开辟空间，创建类的实例(对象)(*)**。

- 在类的里面，方法的外面声明的变量，称为成员变量。

- **成员变量有默认值，而局部变量没有默认值**。

- **成员变量的默认值：byte、short、int默认为0。long默认为0L。float默认为0.0F。double默认为0.0。char默认为'\u0000'。boolean默认为false。引用数据类型默认为null**。

- **局部变量与成员变量的区别？(*)**

  <img src="D:\华信教育\2023下\Java\images\9-10\image-20231019141910798.png" alt="image-20231019141910798" style="zoom:60%;" />

-  java.lang.**NullPointerException**：运行时异常，**空对象异常**。

  - **引用数据类型的变量没有指向堆内存中的对象**。
  - **使用变量调用类的属性或方法**。

  ```java
  public class 人 {
  	String 姓名;
  	int 年龄;
  	String 性别;
  }
  
  public class Test1019 {
  	
  	public static void main(String[] args) {
  		int num = 100;
  		人 p = new 人();
  		p.姓名 = "张斌";
  		p.年龄 = 20;
  		p.性别 = "男";
  
  		System.out.println(p.姓名 + "\t" + p.年龄 + "\t" + p.性别);
  		
  		人 p1 = new 人();
  		p1.姓名 = "曲英杰";
  		p1.年龄 = 25;
  		p1.性别 = "男";
  		System.out.println(p1.姓名 + "\t" + p1.年龄 + "\t" + p1.性别);
  		
  		人 p2 = new 人();
  		System.out.println(p2.姓名 + "\t" + p2.年龄 + "\t" + p2.性别);
  		
  		人 p3 = null;
  		System.out.println(p3.姓名 + "\t" + p3.年龄 + "\t" + p3.性别);
  	}
  
  }
  ```

  ![image-20231019143350160](D:\华信教育\2023下\Java\images\9-10\image-20231019143350160.png)

### 类中的成员方法

- 成员方法的作用：**用于描述类的行为**。

- 成员方法的基本格式：

  ```java
  访问权限 返回类型 方法名([参数列表]) {
      // 方法体
  }
  ```

- **void关键字：表示方法没有返回类型**。

- 方法的作用：

  - 提高代码的重用性。
  - 易于维护。

- 形参与实参

  - 形参：方法声明中的参数。形参是方法的局部变量。
  - 实参：调用方法时传递的参数。

- **面向对象的特征：封装、继承、多态。(*)**

- **类与对象的区别?(*)**

  - **类是概念。**
  - **对象是类具体的实现**。
  
- return关键字

  - **结束方法**。
  - 返回数据。
  - **当方法没有返回类型时，可以使用return语句结束方法，但不能返回数据。(*)**

### 方法的重载/overload(*)

- 在类中有多个**名字相同**，但**参数不同**的**方法**。这些方法称为方法的重载。

- 参数不同：**类型不同、个数不同、顺序不同**。

- **方法的重载只与方法名与参数列表有关，与方法其它的元素无关**。

  ```java
  
  public class 人 {
  	String 姓名;
  	int 年龄;
  	String 性别;
  
  	public void 跑(int count) {
  		if(count <= 0) {
  			return;
  		}
  		
  		for (int i = 1; i <= count; i++) {
  			System.out.println(姓名 + "跑了第" + i + "圈");
  		}
  	}
  	
  	public double sum(int num1, double num2) {
  		return num1 + num2;
  	}
  	
  	public double sum(double num1, int num2) {
  		return num1 + num2;
  	}
  	
  }
  
  public class Test1019 {
  	
  	public static void main(String[] args) {
  		int num = 100;
  		人 p = new 人();
  		p.姓名 = "张斌";
  		p.年龄 = 20;
  		p.性别 = "男";
  		
  		// 编译失败，找到了多个可以调用的sum()方法
  		double i = p.sum(10, 20);
  		System.out.println(i * 10);
  	}
  }
  ```

### 方法参数的传递

- 实参会将**栈**内存中的**数据**传递给形参。

  - 当形参为**基本数据类型**时，实参将**栈**中的**值**传递给了形参。

  - **当形参为基本数据类型时，形参改变实参不变**。

    ```java
    public class Test1020 {
    
    	public static void main(String[] args) {
    		Test1020 t = new Test1020();
    		int num = 10;
    
    		t.method(num);
    		System.out.println(num);
    	}
    
    	public int method(int num) {
    		num += 100;
    		return num;
    	}
    }
    ```

    <img src="D:\华信教育\2023下\Java\images\9-10\image-20231020145719538.png" alt="image-20231020145719538" style="zoom:67%;" />
    
  - 当形参为**引用数据类型**时，实参将栈内存中的**引用**传递给形参。
  
  - **当形参为引用数据类型时，形参改变实参通常也会改变**。
  
    ```java
    public class Test1020 {
    
    	public static void main(String[] args) {
    		Test1020 t = new Test1020();
    		int num = 10;
    
    		t.method(num);
    		System.out.println(num);
    
    		int[] array = { 10, 20, 30 };
    		t.method(array);
    
    		for (int i : array) {
    			System.out.print(i + "\t");
    		}
    	}
    
    	public void method(int[] array) {
    		// 如果数组为空，表示数组不能使用，则结束方法
    		if (array == null || array.length == 0) {
    			return;
    		}
    		array[array.length - 1] = 110;
    	}
    
    	public int method(int num) {
    		num += 100;
    		return num;
    	}
    }
    
    ```
    
  ![image-20231023084500734](D:\华信教育\2023下\Java\images\9-10\image-20231023084500734.png)

### 可变长参数

- 从JDK1.5开始出现。

- 格式：**数据类型... 参数名**

- 可变长参数只能用于方法的形参。

- **可变长参数的本质：一维数组(*)**。

- 可变长参数可以使方法传递参数时更灵活。

- **一个方法中只能出现一个可变长参数。**

- **当方法有多个形参时，可变长参数必须出现在参数列的最后**(*)。

  ```java
  public class Test1023 {
  
  	public static void main(String[] args) {
  		Test1023 t = new Test1023();
  
  		t.method();
  		t.method(100);
  		t.method(10, 20, 30, 40, 50, 60);
  
  	}
  
  	public void method(int... args) {
  		if (args == null || args.length == 0) {
  			return;
  		}
  
  		for (int i : args) {
  			System.out.print(i + "\t");
  		}
  		System.out.println();
  	}
  }
  ```

### 构造方法(构造器)

- **类一定有构造方法**。

- 构造方法的两个特征(*)：
  - **构造方法的名字必须与类名保持一致。**
  - **构造方法一定没有返回类型，并且不能使用void关键字修饰**。

- **当没有在类中书写构造方法时，JVM会自动为类添加默认的构造方法(*)。**

- 默认构造方法的格式

  ```java
  访问权限与类相同 构造方法名() {    
  }
  ```
  
- **当在类中书写了构造方法时，JVM便不会再为类添加默认的构造方法(*)。**

- **构造方法的作用：为类的成员变量初始化(*)**。

- **构造方法也可以重载**。

- **普通方法与构造方法的区别？(*)**

  - **普通方法的名字也可以也类名相同，但普通方法没有返回类型时必须使用void关键字修饰**。**构造方法不能使用void关键字修饰**。
  - **普通方法可以通过类的对象多次调用。通常情况下，构造方法需要在new关键字后面出现，并且一个对象的构造方法只能调用一次**。

### 封装

- 类的**成员变量**使用**private**修饰，**隐藏类实现的细节**。

- 根据需求，为私有的成员变量提供公有的getters**或**setters方法，**提供对外访问的接口**。

- **封装可以提高程序的安全性**。

  ```java
  public class Person {
  	private String name;
  	private int age;
  
  	public Person(String n) {
  		name = n;
  	}
  
  	public Person(String n, int a) {
  		name = n;
  		age = a;
  	}
  
  	public int getAge() {
  		return age;
  	}
  
  	public String getName() {
  		return name;
  	}
  
  	public void printInfo() {
  		System.out.println(name + "\t" + age);
  	}
  
  	public void setAge(int age) {
  		this.age = age;
  	}
  
  	public void setName(String name) {
  		this.name = name;
  	}
  }
  ```

### this关键字与this()语句

- this关键字：对象自身的引用，通过用于调用当前类的成员变量与成员方法。

- this()语句：在类的构造方法中，调用当前类其它的构造方法，必须出现在构造方法的第一行。

  <img src="D:\华信教育\2023下\Java\images\9-10\image-20231026143456788.png" alt="image-20231026143456788" style="zoom:67%;" />

### static关键字

- 修饰成员变量：被static修饰的成员变量称为**静态变量(类变量)**,不使用static修饰的成员变量也称为实例变量。**类所有的对象共用一份静态变量**。

- 修饰成员方法：被static修饰的成员方法称为**静态方法(类方法)**。**静态方法只能直接调用当前类中的静态成员**，非静态的方法可以直接调用当前类中所有的成员。**静态方法中不能出现this与super关键字**。

- **静态的成员可以通过类名(接口名)直接调用，也可以通过类的对象调用(不推荐)。**

  ```java
  public class User {
  
  	static int userId;
  	String userName;
  
  	public User(int userId, String userName) {
  		this.userId = userId;
  		this.userName = userName;
  	}
  
  	public void print() {
  		System.out.println(userId + "\t" + userName);
  	}
  }
  
  public class Test1023 {
  
  	public static void main(String[] args) {
  		// 静态的成员可以通过类名直接调用
  		User.userId = 300;
  
  		User user = new User(100, "AA");
  		// 静态的成员也可以通过类的对象调用，不推荐
  		user.userId = 200;
  	}
  }
  ```

  

### 块(初始化块)

- 在类中或方法中的一对大括号。

  ```java
  public class Test1030 {
  	
  	// 块(初始化块)
  	{
  		System.out.println("调用了块……");
  	}
  	
  	public Test1030() {
  		System.out.println("调用了构造方法……");
  	}
  
  	public static void main(String[] args) {
  		Test1030 t = new Test1030();
          // 程序输出结果：
          /*
          	调用了块……
  			调用了构造方法……
          */
  	}
  }
  ```

### 静态块(静态初始化块)

- **使用static修饰的块，称为静态块**。

- 静态块不能出现在方法中。

  ```java
  public class Test1030 {
  	
  	// 块(初始化块)
  	{
  		System.out.println("调用了块……");
  	}
  	
  	public Test1030() {
  		System.out.println("调用了构造方法……");
  	}
  	
  	// 静态块(静态初始化块)
  	static {
  		System.out.println("调用了静态块……");
  	}
  
  	public static void main(String[] args) {
  		Test1030 t = new Test1030();
  		Test1030 t1 = new Test1030();
  		Test1030 t2 = new Test1030();
          // 程序输出结果：
          /*
          	调用了静态块……
              调用了块……
              调用了构造方法……
              调用了块……
              调用了构造方法……
              调用了块……
              调用了构造方法……
          */
  	}
  }
  ```



### 写出实例变量、静态变量、块、静态块、构造方法加载的顺序以及调用的次数(*)

1. **静态变量：只调用一次，在第一次使用类时初始化。**
2. **静态块：只调用一次，在第一次使用类时调用。**
3. **实例变量：每次创建类的对象时，都会初始化。**
4. **块：每次创建类的对象时调用。**
5. **构造方法：每次创建类的对象时调用。**



### 包(package)

- 包的作用
  - 解决类重名的问题。
  - 管理类。
- **包的本质：文件夹/目录(*)**。
- 当类位于包中时，类**首行代码(注释除外)**必须为**package语句**。
- **类可以直接使用同包中的类**。
- **当类使用其它包中的类时，必须使用import语句导入类(导包)**。
- **java.lang包中的类与接口，JVM会自动导包，不需要手动导入可以直接使用(*)。**
- **直接创建在eclipse的src(default package)下的类与接口，无法使用import语句导包。**



### 使用final修饰的成员变量

- **使用final修饰的成员变量可以在声明时初始化**。

- **如果final修饰的成员变量没有在声明时初始化，则必须在类所有的构造方法中，为final修饰的成员变量初始化。**

  ```java
  public class Person {
  
  	private String name;
  	private final String sex;
  	
  	// 在类所有的构造方法中为final修饰的成员变量赋值
  	public Person() {
  		this.sex = "男";
  	}
  	
  	public Person(String sex) {
  		this.sex = sex;
  	}
  
  	public String getName() {
  		return name;
  	}
  
  	public void setName(String name) {
  		this.name = name;
  	}
  
  	public String getSex() {
  		return sex;
  	}
  
  }
  
  public class Test {
  
  	public static void main(String[] args) {
  		Person p = new Person();
  		p.setName("AA");
  		System.out.println(p.getName() + "\t" + p.getSex());
  		
  		Person p1 = new Person("女");
  		p1.setName("BB");
  		System.out.println(p1.getName() + "\t" + p1.getSex());
  	}
  }
  ```

  

## 继承与多态

- 继承的作用
  - 提高代码的重用性。
  - 易于维护。
  - 易于扩展。
- **Java是单继承：一个类只有一个父类。(*)**
- **extends关键字：描述Java中的继承关系**。
- **子类可以继承父类中所有的成员变量与成员方法**。
- **子类可以继承父类私有的成员，但不能使用。**
- **子类不能继承父类的构造方法**。



### 访问权限

- Java只有**四种**访问权限

  |                    | 类本身 | 同包类 | 非同包子类 | 非同包非子类 |
  | ------------------ | ------ | ------ | ---------- | ------------ |
  | private            | **Y**  | N      | N          | N            |
  | 默认权限（包权限） | **Y**  | **Y**  | N          | N            |
  | protected          | **Y**  | **Y**  | **Y**      | N            |
  | public             | **Y**  | **Y**  | **Y**      | **Y**        |

- **类(顶层类)只能使用public与默认权限修饰。(*)**

- **请写出默认权限与protected哪个权限大？请说明？(*)**

  - **protected权限大。**
  - **默认权限只有类本身与同包中的类可以使用。而protected不但类的本身与同包中的类可以使用，其它包中的子类也可以使用。**



### 方法的重写(方法的覆盖)/override(*)

- **重写的方法要与被重写的方法具有相同的方法名、参数列表、返回类型。**

- 重写方法的**访问权限**必须**大于等于**被重写方法的访问权限。

- 重写方法声明的**异常**必须**小于等于**被重写方法声明的异常。

- static不能产生重写。

  ```java
  package com.test1102;
  
  public class Person {
  	private String name;
  	private int age;
  	
  	public String getName() {
  		return name;
  	}
  
  	public void setName(String name) {
  		this.name = name;
  	}
  
  	public int getAge() {
  		return age;
  	}
  
  	public void setAge(int age) {
  		this.age = age;
  	}
  
  	public void print() {
  		System.out.println(this.name + "\t" + this.age);
  	}
  }
  
  package com.test1102;
  
  public class Student extends Person {
  	private String school;
  
  	public String getSchool() {
  		return school;
  	}
  
  	public void setSchool(String school) {
  		this.school = school;
  	}
  
  	public void print() {
  		System.out.println(this.getName() + "\t" + this.getAge() + "\t" + this.school);
  	}
  }
  
  
  package com.test1102;
  
  public class Test {
  
  	public static void main(String[] args) {
  		Person p = new Person();
  		p.setName("父类");
  		p.setAge(50);
  		p.print();
  		
  		Student s = new Student();
  		s.setName("子类");
  		s.setAge(20);
  		s.setSchool("大连");
  		s.print();
  	}
  }
  ```

  

### super关键字

- super关键字：在子类中引用父类的成员。通常用于，在子类中引用父类同包的成员。



### 继承中的构造方法

- 通常情况下，子类会在自己**构造方法**的**第一行**，默认使用**super()**调用父类**无参**的构造方法。

- **当父类没有无参的构造方法时，子类必须在自己构造方法的第一行，手动调用父类有参数的构造方法，否则编译失败**。

  ```java
  package com.test1102;
  
  public class Person {
  	
  	private String name;
  	private int age;
  	
  	public Person(String name, int age) {
  		System.out.println("父类的构造方法");
  		this.name = name;
  		this.age = age;
  	}
  	
  	public String getName() {
  		return name;
  	}
  
  	public void setName(String name) {
  		this.name = name;
  	}
  
  	public int getAge() {
  		return age;
  	}
  
  	public void setAge(int age) {
  		this.age = age;
  	}
  
  	public void print() {
  		System.out.println(this.name + "\t" + this.age);
  	}
  }
  
  package com.test1102;
  
  public class Student extends Person {
  	
  	private String school;
  	
  	public Student(String name,int age,String school) {
  		super(name,age);
  		System.out.println("子类的构造方法");
  		this.school = school;
  	}
  
  	public String getSchool() {
  		return school;
  	}
  
  	public void setSchool(String school) {
  		this.school = school;
  	}
  
  	public void print() {		
  		System.out.println(this.getName() + "\t" + this.getAge() + "\t" + this.school);
  	}
  }
  
  package com.test1102;
  
  public class Test {
  
  	public static void main(String[] args) {
  		Person p = new Person("父类", 50);
  		p.print();
  		
  		Student s = new Student("子类",20,"大连");
  		s.print();
  	}
  }
  
  ```

  

### 引用数据类型的类型转换

- 比较引用数据类型的大小
  - 父类大。
  - 子类小。

- **当两个类没有继承关系时，不能相互转换**。
- **子类可以直接赋给父类(向上转型)**。向上转型**编译**与**运行**时，永远是正确的。
- **父类必须强转才能赋给子类(向下转型)**。向下转型编译时，永远是正确的。
- 子类的变量必须指向此子类类型的对象。否则运行时抛出异常。
- java.lang.**ClassCastException**：运行时异常，**引用数据类型类型转换异常**。



### 多态

- **多态：父类声明，子类创建**。
- 编译时，多态只能访问父类中的成员，不能访问子类中特有的成员。
- **多态时调用的成员变量一定是父类的。**
- **多态时调用的成员方法**
  - 如果子类没有重写父类的方法，调用父类中的方法。
  - 如果子类重写了父类的方法，则程序运行时方法的指针会动态的从父类的方法绑定到子类的方法(**方法的动态绑定**)，**调用子类的方法**。



### instanceof运算符

- instanceof运算符的作用：判断左面的变量是否为右面类的类型，或右面类子类的类型。
- 当左面的变量与右面的类没有继承关系时，不能使用instanceof进行判断，否则编译失败。



### java.lang.Object类

- 当创建类没有指定父类时，类默认继承于java.lang.Object类。

- **java.lang.Object类：是Java中所有类直接或间接的父类(根类、超类、基类)。(*)**

- **toString()方法：当打印输出类的对象时，或者将类的对象与字符串进行连接时，JVM会自动调用类的toString()方法。(*)**

- **== 与 equals()方法的区别？(*)**

  - == ：判断**栈**内存的内容是否相等。**基本数据类型栈内存中保存的是值，所以基本数据类型可以使用==判断是否相等。引用数据类型栈内存中保存的是引用，所以引用数据类型不推荐使用==判断是否相等。**
  - equals()方法：**判断当前对象与指定的对象是否相等。equals()方法最先出现在Object类中，Object类的equals()方法仍然使用==判断栈内存的内容是否相等。当自定义类的对象需要判断是否相等时，建议重写Object类中的equals()方法。**

  ```java
  package com.test1113;
  
  import java.util.Objects;
  
  public class User {
  
  	private int userId;
  	private String userName;
  
  	public int getUserId() {
  		return userId;
  	}
  
  	public void setUserId(int userId) {
  		this.userId = userId;
  	}
  
  	public String getUserName() {
  		return userName;
  	}
  
  	public void setUserName(String userName) {
  		this.userName = userName;
  	}
  
  	@Override
  	public String toString() {
  		return "User [userId=" + userId + ", userName=" + userName + "]";
  	}
  
  	@Override
  	public int hashCode() {
  		return Objects.hash(userId);
  	}
  
  	@Override
  	public boolean equals(Object obj) {
  		if (this == obj)
  			return true;
  		if (obj == null)
  			return false;
  		if (getClass() != obj.getClass())
  			return false;
  		User other = (User) obj;
  		return userId == other.userId;
  	}
  
  }
  
  package com.test1113;
  
  public class Test {
  
  	public static void main(String[] args) {
  		int x = 100;
  		int y = 100;
  		
  		User user = new User();
  		user.setUserId(100);
  		user.setUserName("张三");
  		
  		User user1 = new User();
  		user1.setUserId(100);
  		user1.setUserName("张三");
  		
  		User user2 = user;
  		
  		System.out.println(x == y); // true
  		System.out.println(user == user1); // false
  		System.out.println(user == user2); // true
  		
  		System.out.println(user.equals(user1)); // true
  		System.out.println(user.equals(user2)); // true
  	}
  
  }
  ```

  <img src="D:\华信教育\2023下\Java\images\9-10\image-20231113094110912.png" alt="image-20231113094110912" style="zoom:80%;" />



## 抽象(abstract)

- 修饰类：抽象类。**不能创建抽象类的对象**(不能new)。**只能创建抽象类子类的对象**。**抽象类也存在构造方法**(因为子类会在自己构造方法的第一行，调用父类的构造方法)。

- 修饰方法：抽象方法。**抽象方法只有方法的声明，没有方法的实现**。**抽象方法所在的类必须是抽象类**。**非抽象的方法可以直接调用当前类中抽象的方法**。
  - 当抽象类的**子类不是抽象类**时，**子类必须重写抽象类中所有的抽象方法**。
  - 当抽象类的**子类**也**是抽象类**时，子类可以**不重写**抽象类中的**抽象方法**，或**只重写部分抽象方法**。
- 修饰接口
- **final关键字(*)**
  - **修饰常量：只能赋值一次。**
  - **修饰方法：子类不能重写。**
  - **修饰类：类不能被继承。**
- **阻止类被继承有几种方式？分别是什么？(*)**
  - **使用final修饰类。**
  - **使用private修饰类的构造方法**。(因为子类会在自己构造方法中调用父类的构造方法，如果父类的构造方法是私有的，子类将无法访问父类的构造方法，则无法继承。)
- **abstract不能与哪些关键字一起使用？(*)**
  - **private**
  - **static**
  - **final**



## 接口(interface)

- **接口的作用：使Java可以实现多继承。(*)**
- 接口是一组**常量**与**抽象方法**的集合。
  - **接口中的常量一定使用public static final修饰。使用static final修饰的常量必须在声明时初始化。**
  - **接口中的方法一定使用public abstract修饰。**
- 类与接口的关系
  - 类可以**实现(implements)**接口。
  - 当接口的实现类**不是抽象类**时，实现类**必须重写接口中所有的抽象方法**。
  - 当接口的实现类**是抽象类**时，实现类可以**不重写**接口中的**抽象方法**，或**只重写部分的抽象方法**。
  - **一个类可以实现多个接口。**
- 接口与接口的关系 
  - 接口可以**继承(extends)**接口。
  - **一个接口可以继承多个接口。**
- **接口不是类**。**不能创建接口的对象(不能new)**。**只能创建接口实现类的对象**。**接口与Object类没有关系**。
- **抽象类与接口的区别？(自行总结)(*)**



## 内部类

- Java有4种内部类
  - 实例内部类
  - 静态内部类
  - 匿名内部类
  - 局部内部类
- 内部类：在一个类内部创建的另一个类。
- **外部类与内部类的区别?(*)**
  - 外部类只能使用public与默认的访问权限修饰。内部类可以使用所有的访问权限修饰。
  - 外部类不能使用static修饰，而内部类可以使用static修饰。

### 实例内部类

- **实例内部类可以直接访问外部类所有的成员(包括私有的)**。

  ```java
  package com.test1120;
  
  // 顶层类/外部类
  public class OuterClass {
  	
  	private int id = 100;
  
  	// 实例内部类
  	public class InnerClass {
  		
  		private int id = 200;
  		
  		public void method() {
  			System.out.println(this.id); // 200
  			// 在内部类访问外部类的this对象
  			System.out.println(OuterClass.this.id); // 100
  		}
  	}
  }
  
  package com.test1120;
  
  public class Test {
  
  	public static void main(String[] args) {
  		// 创建外部类的对象
  		OuterClass outer = new OuterClass();
  		// 借助于外部类的对象，创建内部类的对象
  		OuterClass.InnerClass inner = outer.new InnerClass();
  		inner.method();
  	}
  
  }
  
  ```



### 静态内部类

- **静态内部类只能直接访问外部类静态的成员(包括私有的)。**

  ```java
  package com.test1120;
  
  // 顶层类/外部类
  public class OuterClass {
  	
  	private static int id = 100;
  
  	// 静态内部类
  	public static class InnerStaticClass {
  		
  		public void method() {
  			System.out.println(id);
  		}
  	}
  }
  
  package com.test1120;
  
  public class Test {
  
  	public static void main(String[] args) {
  		// 创建静态内部类的对象
  		OuterClass.InnerStaticClass inner = new OuterClass.InnerStaticClass();
  		inner.method();
  	}
  
  }
  
  ```



### 局部内部类

- 在方法中或块中创建的内部类。

- 局部内部类不能使用访问权限修饰。

- 局部内部类不能使用static修饰。

- 局部内部类可以直接访问所在方法中的局部变量。

  ```java
  package com.test1120;
  
  // 顶层类/外部类
  public class OuterClass {
  	
  	private int id1 = 100;
  
  	public void method() {
  		int id2 = 200;
  		
  		// 局部内部类
  		class InnerClass {
  			
  			public void method() {
  				System.out.println(id1);
  				// 直接访问方法中的局部变量
  				System.out.println(id2);
  			}
  		}
  		
  		// 创建局部内部类的对象
  		InnerClass inner = new InnerClass();
  		inner.method();
  	}
  }
  
  ```


#### 匿名内部类

- 示例

  ```java
  package com.test1123;
  
  import java.awt.Color;
  import java.awt.event.ActionEvent;
  import java.awt.event.ActionListener;
  
  import javax.swing.JButton;
  import javax.swing.JFrame;
  
  public class MyFrame extends JFrame {
  
  	private JButton btn1;
  	private JButton btn2;
  	private JButton btn3;
  
  	public MyFrame() {
  		// 设置当前窗体的布局管理器为null
  		this.setLayout(null);
  		// 设置当前窗体的标题
  		this.setTitle("我的第一个Java窗体");
  		// 设置当前窗体在显示器中的位置与大小
  		this.setBounds(200, 200, 400, 300);
  		// 设置当前窗体不能改变大小
  		this.setResizable(false);
  		// 设置窗体默认的关闭事件
  		this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
  
  		// 创建按钮
  		btn1 = new JButton("红色");
  		// 设置按钮在窗体中的位置与大小
  		btn1.setBounds(50, 200, 75, 25);
  		// 将按钮添加到窗体的内容面板中
  		this.getContentPane().add(btn1);
  		// 创建监听器，监听按钮的单击事件
  		btn1.addActionListener(new ActionListener() {
  			@Override
  			public void actionPerformed(ActionEvent e) {
  				// 设置窗体内容面板的背景颜色为红色
  				MyFrame.this.getContentPane().setBackground(Color.RED);
  			}
  		});
  
  		btn2 = new JButton("绿色");
  		btn2.setBounds(155, 200, 75, 25);
  		this.getContentPane().add(btn2);
  		btn2.addActionListener(new ActionListener() {			
  			@Override
  			public void actionPerformed(ActionEvent e) {
  				MyFrame.this.getContentPane().setBackground(Color.GREEN);
  			}
  		});
  
  		btn3 = new JButton("蓝色");
  		btn3.setBounds(260, 200, 75, 25);
  		this.getContentPane().add(btn3);
  		btn3.addActionListener(new ActionListener() {			
  			@Override
  			public void actionPerformed(ActionEvent e) {
  				MyFrame.this.getContentPane().setBackground(Color.BLUE);
  			}
  		});
  
  		// 显示窗体
  		this.setVisible(true);
  	}
  
  	public static void main(String[] args) {
  		new MyFrame();
  	}
  }
  
  ```



## Lambda表达式

- 从JDK1.8开始出现。

- 函数式接口
  - **有且只有一个抽象方法的接口。(*)**
  - **@FunctionalInterface注解：检查接口是否为函数式接口。**
  
- Lambda表达式：语法糖。

  - 当方法只有一个参数时，参数列表的小括号可以省略。
  - 当方法体中只有一行代码，大括号可以省略。
  - 当大括号省略时，return关键字必须省略。

  ```java
  package com.test1123;
  
  public class Test {
  	public static void main(String[] args) {
  //		TestInterface1 t1 = new TestInterface1() {
  //			@Override
  //			public void test() {
  //				System.out.println("没有返回类型，没有参数");
  //			}
  //		};
  		TestInterface1 t1 = () -> System.out.println("没有返回类型，没有参数");
  		t1.test();
  
  //		TestInterface2 t2 = new TestInterface2() {
  //			@Override
  //			public void test(int num1) {
  //				System.out.println("没有返回类型，有一个参数：" + num1);
  //			}
  //		};
  		TestInterface2 t2 = n -> System.out.println("没有返回类型，有一个参数：" + n);
  		t2.test(100);
  
  //		TestInterface3 t3 = new TestInterface3() {
  //			@Override
  //			public void test(int num1, int num2) {
  //				System.out.println("没有返回类型，两个参数的和：" + (num1 + num2));
  //			}
  //		};
  		TestInterface3 t3 = (n,m) -> System.out.println("没有返回类型，两个参数的和：" + (n + m));
  		t3.test(100, 200);
  
  //		TestInterface4 t4 = new TestInterface4() {
  //			@Override
  //			public int test() {
  //				return (int) (Math.random() * 100 + 1);
  //			}
  //		};
  		TestInterface4 t4 = () -> (int) (Math.random() * 100 + 1);
  		System.out.println(t4.test());
  
  //		TestInterface5 t5 = new TestInterface5() {
  //			@Override
  //			public int test(int num1) {
  //				return num1 * 100;
  //			}
  //		};
  		TestInterface5 t5 = n -> n * 100;
  		System.out.println(t5.test(200));
  
  //		TestInterface6 t6 = new TestInterface6() {
  //			@Override
  //			public int test(int num1, int num2) {
  //				return num1 * num2;
  //			}
  //		};
  		TestInterface6 t6 = (n,m) -> n * m;
  		System.out.println(t6.test(100, 200));
  	}
  }
  
  @FunctionalInterface
  interface TestInterface1 {
  	public abstract void test();
  }
  
  @FunctionalInterface
  interface TestInterface2 {
  	public abstract void test(int num1);
  }
  
  @FunctionalInterface
  interface TestInterface3 {
  	public abstract void test(int num1, int num2);
  }
  
  @FunctionalInterface
  interface TestInterface4 {
  	public abstract int test();
  }
  
  @FunctionalInterface
  interface TestInterface5 {
  	public abstract int test(int num1);
  }
  
  @FunctionalInterface
  interface TestInterface6 {
  	public abstract int test(int num1, int num2);
  }
  
  ```

- 示例

  ```java
  package com.test1123;
  
  import java.util.Arrays;
  import java.util.Comparator;
  
  public class TestSort {
  
  	public static void main(String[] args) {
  		// 创建长度为10的数组，用于保存10个用户信息
  		User[] userArray = new User[10];
  
  		// 使用循环向数组中添加10个用户信息
  		for (int i = 0; i < userArray.length; i++) {
  			// 创建新用户
  			User user = new User();
  			// 设置新用户的名字与年龄
  			user.setUserName("User" + i);
  			user.setUserAge((int) (Math.random() * 100 + 1));
  			// 将新用户添加到用户数组中
  			userArray[i] = user;
  		}
  
  		// 输出排序前用户信息 -> forEach循环
  		for (User user : userArray) {
  			System.out.println(user);
  		}
  		System.out.println("-----------------------");
  		// 输出排序前用户信息 -> Lambda表达式
  //		Arrays.stream(userArray).forEach(new Consumer<User>() {
  //			@Override
  //			public void accept(User t) {
  //				System.out.println(t);
  //			}
  //		});
  		Arrays.stream(userArray).forEach(t -> System.out.println(t));
  
  		// 根据用户年龄，对用户数组进行排序
  //		Arrays.sort(userArray,new Comparator<User>() {
  //			/*
  //			 * 当第一个参数大于第二个参数，返回正数
  //			 * 当第一个参数小于第二个参数，返回负数
  //			 * 当第一个参数等于第二个参数，返回0
  //			 */
  //			@Override
  //			public int compare(User o1, User o2) {	
  //				if(o1.getUserAge() > o2.getUserAge()) {
  //					return 1;
  //				} else if (o1.getUserAge() < o2.getUserAge()) {
  //					return -1;
  //				} else {
  //					return 0;
  //				}
  //			}
  //		});
  		Arrays.sort(userArray, (o1, o2) -> o1.getUserAge() - o2.getUserAge());
  		
  		// 输出排序后的用户信息
  		System.out.println("--------------------");
  		Arrays.stream(userArray).forEach(t -> System.out.println(t));
  
  	}
  
  }
  
  ```




## 异常处理

### 异常结构

<img src="D:\华信教育\2023下\Java\images\9-10\image-20231130135447370.png" alt="image-20231130135447370" style="zoom:67%;" />

- **java.lang.Throwable类：是Java中所有错误与异常的父类。**
- **java.lang.Error类：是应用程序不应该捕获或处理的严重的问题。**
- **java.lang.Exception类：是应用程序应该捕获与处理的异常。**
- **非运行时异常：在编写程序时，必须捕获或处理的异常。否则.java文件无法编译为.class文件，程序不能运行。**
- **java.lang.RuntimeException及其子类(运行时异常)：在编写程序时，可以不捕获与处理的异常。程序可以运行，但运行时可能抛出异常。**



### try..catch..finally

- 格式

  ```java
  try {
      // 捕获异常，存放可能发生异常的代码。
  } catch (Throwable 参数名) {
      // 处理异常，存放处理异常的代码。
  } finally {
      // 一定执行的代码。
  }
  ```

- **try块不能单独使用**，必须与catch**或**finally块一起使用。

- 一个try语句中可以出现0个或N个catch块。

- 当try块中没有抛出异常时，catch块中的代码不会执行。

- **当try块中的代码抛出异常时，try块中的代码会终止执行。跳转到catch块中处理异常。**

- **可以使用Exception在catch块中处理所有的异常。**

- **Exception必须出现在最后一个catch块中。**

- **无论程序是否发生异常，finally块中的代码一定会执行。**

- **如果try语句中存在finally块，try与catch块中的return语句会暂停执行，等待finally块执行完毕后，再继续执行return语句。**

- **工作中不推荐在finally块中出现return语句。如果finally块中出现return语句，则try与catch中的return语句全部失效。**

  ```java
  package com.test1130;
  
  public class TestFinally {
  
  	public static void main(String[] args) {
  		int i = method();
  		System.out.println(i);
  	}
  
  	public static int method() {
  		try {
  			System.out.println("try……");
  			return 1;
  		} catch (Exception e) {
  			System.out.println("catch……");
  			return 2;
  		} finally {
  			System.out.println("finally……");
  			return 3;
  		}
  	}
  }
  
  ```

- **请写出final、finally、finalize()的区别？(*)**

  - **final关键字**
    - **修饰常量：只能赋值一次。**
    - **修饰方法：方法不能被重写。**
    - **修饰类：类不能被继承。**
  - **finally：Java异常处理的一部分。无论程序是否发生异常，finally中的代码一定会执行。**
  - **finalize()方法(析构方法)：Object类提供的方法。当垃圾回收器销毁对象之前，自动调用此方法，释放内存。**



### throw与throws关键字(*)

- throw：在**方法体的内部**，手动抛出**一个**异常。可以结束方法。
- throw**s**：在**方法声明的最后**，说明调用此方法时，方法可能会抛出**哪些**异常。



### 异常与方法的重写

- **当父类被重写的方法声明了1个或N个异常时，子类重写的方法可以声明0个异常**。

- **当子类重写的方法也声明了异常时，子类重写的方法可以声明与父类相同的异常，或父类声明异常的子异常**。

  ```java
  package com.test1204;
  
  import java.io.IOException;
  
  public class Person {
  
  	public void method() throws IOException {
  		System.out.println("父类的方法");
  	}
  }
  
  package com.test1204;
  
  import java.io.IOException;
  import java.util.zip.ZipException;
  
  import javax.annotation.processing.FilerException;
  
  public class Student extends Person {
  
  	// ZipException,FilerException是IOException的子异常
  	public void method() throws IOException,ZipException,FilerException {
  		System.out.println("子类的方法");
  	}
  }
   
  
  ```



### 异常与构造方法

- **构造方法也可以使用throws声明异常。**

- **当父类的构造方法声明了异常时，子类的构造方法可必须声明相同的异常，或父类声明异常的父异常。**

  ```java
  package com.test1204;
  
  import java.io.IOException;
  
  public class Person {
  	
  	public Person() throws IOException {		
  	}
  }
  
  package com.test1204;
  
  import java.io.IOException;
  import java.util.zip.ZipException;
  
  import javax.annotation.processing.FilerException;
  
  public class Student extends Person {
  	
  	public Student() throws IOException,Exception {
  		super();
  	}
  }
   
  
  ```



### 创建自定义的异常类(*)

- **使类继承于Exception或Exception的子类**。



## 常用类

### 包装类(装箱类)

- Java中有8个包装类。

- 包装类可以提供对应数据类型常用的属性与方法。

- 包装类：**Byte、Short、Long、Float、Double、Boolean、Integer、Character**。

- **装箱与拆箱(*)**

  - **装箱：将基本数据类型转换为包装类。**
  - **拆箱：将包装类转换为基本数据类型。**
  - **从JDK1.5开始，Java可以自动装箱与拆箱。**
  - **自动装箱与拆箱可以简化代码，但不会提高程序进行的效率。**

- **使用包装类的parseXXX()方法，可以将String转换为对应的基本数据类型。**

- **使用包装类的valueOf()方法，可以将String转换为对应的包装类。**

  ```java
  package com.test1207;
  
  public class Test {
  
  	public static void main(String[] args) {
  		// 提供与类型相关的属性
  		System.out.println(Integer.MAX_VALUE);
  		System.out.println(Long.MIN_VALUE);
  		System.out.println(Double.MAX_VALUE);
  		// 提供与类型相关的方法
  		System.out.println(Integer.toBinaryString(100)); // 十进制转换二进制
  		System.out.println(Integer.toOctalString(100));  // 十进制转换八进制
  		System.out.println(Integer.toHexString(100));    // 十进制转换十六进制
  		
  		int num1 = 100;
  		// 装箱
  		Integer num2 = Integer.valueOf(num1);
  		// 拆箱
  		int num3 = num2.intValue();
  		
  		// 自动装箱
  		Integer num4 = 100;
  		// 自动装箱
  		int num5 = num4;
  		
  		String s = "100";
  		// 将String转换为基本数据类型
  		int x = Integer.parseInt(s);
  		System.out.println(x);		
  		double y = Double.parseDouble(s);
  		System.out.println(y);		
  		float z = Float.parseFloat(s);
  		System.out.println(z);
  		
  		String s1 = "2000";
  		// 将String转换为包装类
  		Integer x1 = Integer.valueOf(s1);
  		System.out.println(x1);
  		Double y1 = Double.valueOf(s1);
  		System.out.println(y1);
  		Float z1 = Float.valueOf(s1);
  		System.out.println(z1);
  	}
  }
  
  ```

  

### 大数字

- java.math.BigInteger：大整数。

- java.math.BigDecimal：大浮点数，在进行浮点数运算时，不会产生误差。

  ```java
  BigDecimal num1 = new BigDecimal("6987984654968743651354874651684.654326359856543213568");
  BigDecimal num2 = new BigDecimal("2334566888136576434658468531323.546897632131687635416");
  
  // 加
  System.out.println(num1.add(num2));
  // 减
  System.out.println(num1.subtract(num2));
  // 乘
  System.out.println(num1.multiply(num2));
  // 除
  System.out.println(num1.divide(new BigDecimal(2)));
  ```



### java.util.Date类

- java.util.Date类：日期类。通常用于获得当前日期+时间，或用于日期的比较。

  ```java
  // 获得当前日期+时间
  Date date = new Date();
  System.out.println(date);
  
  // getTime()返回类型为long类型，从1970-1-1 00:00:00到创建Date对象之间的毫秒数
  System.out.println(date.getTime());
  // 日期比较
  Date date1 = new Date();
  // 判断date是否早于date1
  System.out.println(date.before(date1));
  // 判断date是否晚于date1
  System.out.println(date.after(date1));
  // 判断date是否等于date1
  System.out.println(date.equals(date1));
  ```

### java.util.Calendar类

- java.util.Calendar类：日历类，通常用于查询日期详细信息，或用于日期的计算。

  ```java
  Calendar c = Calendar.getInstance();
  // 获得日期详细信息
  System.out.println(c);
  System.out.println(c.get(Calendar.YEAR));
  System.out.println(c.get(Calendar.MONTH) + 1);
  System.out.println(c.get(Calendar.DATE));
  System.out.println(c.get(Calendar.DAY_OF_YEAR));
  System.out.println(c.get(Calendar.WEEK_OF_YEAR));
  // 日期计算：通常用于自动计算截止时间
  c.add(Calendar.MONTH, 24);
  System.out.println(c.get(Calendar.YEAR));
  System.out.println(c.get(Calendar.MONTH) + 1);
  System.out.println(c.get(Calendar.DATE));
  ```

  



### java.text.DateFormat类及其子类

- java.text.DateFormat类及其子类：通常用于，Date与String的转换。

  ```java
  // 创建SimpleDateFormat的对象，并设置日期的格式
  SimpleDateFormat sdf = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss");
  Date date2 = new Date();
  // 将Date转换为String
  String s = sdf.format(date2);
  System.out.println(s);
  
  s = "2020-10-20 15:36:47";
  // 将String转换为Date
  try {
      date2 = sdf.parse(s);
      System.out.println(date2);
  } catch (ParseException e) {
      System.out.println("日期格式不正确！！！");
  }
  ```



### java.time.LocalDate、java.time.LocalTime、java.time.LocalDateTime类

- 这三个类从JDK1.8开始出现。

- 这三个类均为**不可变**的并且是**线程安全**的。

  ```java
  // 获得当前日期+时间
  LocalDateTime dateTime = LocalDateTime.now();
  System.out.println(dateTime);
  
  // 获得日期详细信息
  System.out.println(dateTime.getYear());
  System.out.println(dateTime.getMonth()); // 获得月份(英文)
  System.out.println(dateTime.getMonthValue()); // 获得月份(数字)
  System.out.println(dateTime.getDayOfMonth());
  System.out.println(dateTime.getDayOfYear());
  
  // 日期计算		
  System.out.println(dateTime.plusDays(100));  // 加天
  System.out.println(dateTime.plusDays(-100)); // 减天
  System.out.println(dateTime.plusMonths(24)); // 加月
  ```




### 泛型

- 从JDK1.5开始出现。

- **泛型的作用：后期绑定数据类型。**

- **如果没有指定泛型的类型，泛型默认为java.lang.Object类**。

- **X extends Y：设置泛型X只能为Y或Y子类的类型。**

- **X super Y：设置泛型X是Y或Y的父类类型。**

- **泛型只能使用引用数据类型。**

  ```java
  package com.test1214;
  
  public class Point<T extends Number> {
  
  	private T x;
  	private T y;
  
  	public T getX() {
  		return x;
  	}
  
  	public void setX(T x) {
  		this.x = x;
  	}
  
  	public T getY() {
  		return y;
  	}
  
  	public void setY(T y) {
  		this.y = y;
  	}
  
  	@Override
  	public String toString() {
  		return "Point [x=" + x + ", y=" + y + "]";
  	}
  }
  
  package com.test1214;
  
  public class Test {
  
  	public static void main(String[] args) {
  		Point<Integer> p1 = new Point<>();
  		p1.setX(120);
  		p1.setY(76);
  		System.out.println(p1);
  		
  		Point<Double> p2 = new Point<>();
  		p2.setX(36.75);
  		p2.setY(75.39);
  		System.out.println(p2);
  	}
  }
  
  ```

  

### java.lang.String类

- String是Java中**不可变**的字符序列。

- **当修改String的内容时会产生新的String对象。当需要大量修改字符串时，不建议使用String类型。**

- **String重写了Object类中的equals()方法，用于判断两个字符串的内容是否相等。**

  ```java
  String s1 = "abc";
  String s2 = "abc";
  String s3 = new String("abc");
  
  System.out.println(s1 == s2); // true
  System.out.println(s1 == s3); // false
  System.out.println(s1.equals(s2)); // true
  System.out.println(s1.equals(s3)); // true
  ```

  **![image-20231214144404337](D:\华信教育\2023下\Java\images\9-10\image-20231214144404337.png)**

- **String s = new String("abc");该行代码创建了几个String对象？(*)**
  
  - 创建了两个String对象。





### java.lang.StringBuffer与java.lang.StringBuilder类

- StringBuffer与StringBuilder是Java中**可变的**字符序列。

- **每次对StringBuffer与StringBuilder的修改不会产生新的字符串对象。所以如果需要大量修改字符串时，建议使用StringBuffer或StringBuilder。**

- **StringBuffer与StringBuilder的区别？(*)**

  - **StringBuffer是线程安全的。**
  - **StringBuilder是线程不安全的。在不考虑线程安全的情况下，建议使用，效率比StringBuffer高。**

-  java.lang.**StringIndexOutOfBoundsException**：运行时异常，字符串下标越界异常。

- **StringBuffer与StringBuilder没有重写Object类中的equals()方法，不能使用equals()方法判断内容是否相等**。

- **StringBuffer与StringBuilder的方法会改变自身的内容**。

  ```java
  StringBuilder s1 = new StringBuilder("abc");
  System.out.println(s1);
  
  // 在字符串的末尾追加内容
  s1.append("def1234567890");
  System.out.println(s1);
  
  // 从下标为2的位置开始删除字符串，删除到下标为6的位置之前(半包含)
  s1.delete(2, 6);
  System.out.println(s1);
  
  // 删除指定位置的字符
  s1.deleteCharAt(5);
  System.out.println(s1);
  
  // 在指定的位置之前，插入内容
  s1.insert(0, "Java");
  System.out.println(s1);
  
  // 释放字符串对空闲的内存
  s1.trimToSize(); 
  
  StringBuilder s2 = new StringBuilder("abc");
  StringBuilder s3 = new StringBuilder("abc");
  System.out.println(s2 == s3); // false
  System.out.println(s2.equals(s3)); // false
  System.out.println(s2.toString().equals(s3.toString())); // true
  ```



### 常用集合

- 常用集合的结构

  ![image-20231218092852322](D:\华信教育\2023下\Java\images\9-10\image-20231218092852322.png)

- **Set、List、Map的区别？(*)**
  - **Set：不能保存重复值，不能保存元素加入的顺序。**
  - **List：可以保存重复值，可以保存元素加入的顺序。**
  - **Map：每次保存一对键值(Key-Value)对，键不能重复，值可以重复。**



### java.util.Set接口

- **java.util.TreeSet类：创建时不能指定集合的长度(默认长度为0)，集合中的元素以升序排序**。

- **java.util.HashSet类：创建时可以指定集合的长度(默认长度为16)。集合中的元素根据元素的hashCode进行排序。**

  ```java
  // 创建长度为0的Set集合
  // TreeSet<String> set = new TreeSet<>();
  // 默认创建长度为16的集合
  // HashSet<String> set = new HashSet<>();
  // 创建指定长度的集合
  HashSet<String> set = new HashSet<>(100);
  
  set.add("123");
  set.add("456");
  set.add("CC");
  set.add("BB");
  set.add("FF");		
  set.add("AA");
  set.add("DD");
  set.add("EE");
  
  
  System.out.println(set);
  // 清空集合
  // set.clear();
  // System.out.println(set);
  
  // 移除集合中指定的元素，成功返回true,否则返回false
  System.out.println(set.remove("AA"));
  System.out.println(set);
  // 返回集合中元素的个数
  System.out.println(set.size());
  // 判断集合中是否存在指定的元素
System.out.println(set.contains("EE"));
  // 判断集合是否为空
  System.out.println(set.isEmpty());
  
  // 遍历Set集合的方法一：迭代器
  // 将Set集合中的数据复制到迭代器中
  System.out.println("-----------方法一-----------");
  Iterator<String> it = set.iterator();
  // 遍历迭代器，获得所有数据
  // hasNext()：判断迭代器当前指针的下一个位置是否存在数据
  while(it.hasNext()) {
      // next()：将指针向下移动一个位置，并返回指针指向的数据
      System.out.println(it.next());
  }
  
  // 遍历Set集合的方法二：forEach循环
  System.out.println("-----------方法二-----------");
  for (String s : set) {
      System.out.println(s);
  }
  
  // 遍历Set集合的方法三：stream()
  System.out.println("-----------方法三-----------");
  set.stream().forEach(t -> System.out.println(t));
  
  // 遍历Set集合的方法四：Lambda表达式
  System.out.println("-----------方法四-----------");
  set.forEach(t -> System.out.println(t));
  
  // 简化Lambda表达式
  System.out.println("-----------简化-----------");
  set.forEach(System.out::println);
  ```
  
  

### java.util.List接口

- **ArrayList、LinkedList、Vector的区别？(*)**

  - **ArrayList类：底层使用数组实现。查询数据时效率高，插入与删除数据时效率低。**
  - **LinkedList类：底层使用链表实现。查询数据时效率低，插入与删除数据时效率高。**
  - Vector类：功能与ArrayList相似。Vector安全的，ArrayList是线程不安全的。

- 示例：

  ```java
  // 创建长度为0的集合
  // LinkedList<String> list = new LinkedList<>();
  // 创建默认为长为10的集合
  // ArrayList<String> list = new ArrayList<>();
  // 创建指定长度的集合
  ArrayList<String> list = new ArrayList<>(100);
  
  list.add("CC");
  list.add("FF");
  list.add("AA");
  list.add("DD");
  list.add("BB");
  list.add("AA");
  list.add("EE");
  
  System.out.println(list);
  // 判断集合中是否存在指定的元素
  System.out.println(list.contains("BB"));
  // 返回集合中元素的个数
  System.out.println(list.size());
  // 判断集合是否为空
  System.out.println(list.isEmpty());
  // 获得集合中指定位置的数据，如果下标越界，则运行时抛出异常
  System.out.println(list.get(2));
  // 在集合中查找指定元素首次出现的位置，没找到返回-1
  System.out.println(list.indexOf("AA"));
  // 在集合中查找指定元素最后出现的位置，没找到返回-1
  System.out.println(list.lastIndexOf("AA"));
  // 判断指定的元素是否出现了一次
  System.out.println((list.indexOf("BB") == list.lastIndexOf("BB") ? "只出现了一次" : "出现了多次"));
  // 移除集合中指定位置的元素，移除成功返回被移除的元素，如果下标越界，则运行时抛出异常
  System.out.println(list.remove(3));
  System.out.println(list);
  // 移除集合中首次出现的元素，成功返回true,否则返回false
  System.out.println(list.remove("AA"));
  System.out.println(list);
  // 释放集合中空闲的内存
  list.trimToSize();
  
  // 遍历List集合方法一：for循环
  System.out.println("----------方法一---------");
  for(int i = 0 ; i < list.size() ; i++) {
      System.out.println(list.get(i));
  }
  
  // 遍历List集合方法二：forEach循环
  System.out.println("----------方法二---------");
  for (String s : list) {
      System.out.println(s);
  }
  
  // 遍历List集合方法三：stream()
  System.out.println("----------方法三---------");
  // list.stream().forEach(t -> System.out.println(t));
  list.stream().forEach(System.out::println);
  
  // 遍历List集合方法四：stream
  System.out.println("----------方法四---------");
  // list.forEach(t -> System.out.println(t));
  list.forEach(System.out::println);
  
  ArrayList<Integer> list1 = new ArrayList<>();
  
  list1.add(100);
  list1.add(200);
  list1.add(300);
  list1.add(400);
  list1.add(500);
  list1.add(600);
  
  // 过滤集合：当集合中大于等于400的数据取出来
  //		List<Integer> list2 = list1.stream().filter(new Predicate<Integer>() {
  //			@Override
  //			public boolean test(Integer t) {
  //				if(t >= 400)
  //					return true;
  //				return false;
  //			}
  //		}).toList();
  //		System.out.println(list2);
  List<Integer> list2 = list1.stream().filter(t -> t >= 400).toList();
  System.out.println(list2);
  ```

  

### java.util.Map接口

- **java.util.Hashtable类：线程安全的。不允许使用null作为键或值。**

- **java.util.HashMap类：线程不安全的。允许使用null作为键或值。**

- **JDK1.7的HashMap与JDK1.8的HashMap的区别？(*)**

  - JDK1.7的HashMap
    - JDK1.7中的HashMap使用了**数组+链表（散列表）**的数据结构。
    - JDK1.7的链表在扩容时使用的是**头插**法。
  - JDK1.8的HashMap
    - JDK1.8的HashMap使用了**数组+链表+红黑树**的数据结构。
    - JDK1.8的链表在扩容时使用的是**尾插**法。
    - **当HashMap中的数据个数超过64个时，并且某个链表的长度超过8时。这个链表会转化为红黑树(树化)**。

  ```java
  // 创建默认长度为16的集合，如果集合的长度不足，默认根据集合长度的0.75自动扩展集合
  // HashMap<Integer,String> map = new HashMap<>();
  // 创建指定长度的集合，如果集合的长度不足，默认根据集合长度的0.75自动扩展集合
  HashMap<Integer,String> map = new HashMap<>(100);
  
  map.put(100, "AA");
  map.put(200, "BB");
  map.put(300, "CC");
  map.put(400, "DD");
  map.put(500, "EE");
  map.put(600, "FF");
  
  System.out.println(map);
  // 判断集合中是否存在指定的键
  System.out.println(map.containsKey(300));
  // 判断集合中是否存在指定的值
  System.out.println(map.containsValue("QQ"));
  // 获得集合中指定键对应的值，如果键不存在，返回null
  System.out.println(map.get(200));
  // 返回集合中键值对的个数
  System.out.println(map.size());
  // 移除集合中指定键对应的键值对，移除成功返回键对应的值，如果移除失败，返回null
  System.out.println(map.remove(3000));
  System.out.println(map);
  
  // 遍历Map集合方法一：Set + 迭代器
  System.out.println("-------------方法一--------------");
  // 将Map中所有的键复制到Set集合中
  Set<Integer> keySet = map.keySet();
  // 将Set中所有的键复制到迭代器中
  Iterator<Integer> it = keySet.iterator();
  // 遍历迭代器中所有的键，通过键获得Map中所有的值
  while (it.hasNext()) {
      // 获得迭代器中的键
      Integer key = it.next();
      // 根据键获得Map集合中对应的值
      String value = map.get(key);
      System.out.println(key + " : " + value);
  }
  
  // 遍历Map集合方法二：Entry + forEach循环
  System.out.println("-------------方法二--------------");
  // 将Map集合中的每个键值对，保存到Set集合中
  Set<Entry<Integer, String>> entrySet = map.entrySet();
  for (Entry<Integer, String> entry : entrySet) {
      System.out.println(entry.getKey() + " : " + entry.getValue());
  }
  
  // 遍历Map集合方法三：Lambda表达式
  System.out.println("-------------方法三--------------");
  map.forEach((k, v) -> System.out.println(k + " : " + v));
  ```
