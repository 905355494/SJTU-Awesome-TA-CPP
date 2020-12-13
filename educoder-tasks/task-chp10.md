# 实训作业参考答案 —— 第十章 类(上、下)


## 10.1.1 任务名称

个人成绩单类

## Description

实现一个个人成绩单类。

## Note
本题提供了main.cpp. class.h。你只需要编辑class.cpp，本题中不需要编辑其他文件。

## Input Format

输入
输入多个在[0, 6]中的数字（用数字代表所需操作），（其中若输入0，紧接着后面输入三个整数：num1， num2， num3），用-1代表结束操作

## Output Format

输出
相应操作的输出


## Sample Input
```
0 23 45 78
1
2
3
4
5
6
-1
```
## Sample Output
```
00000000 name 23 45 78
78
23
no
no
yes
```

## Explanation

解释
在输入操作数之前，需提前创建好一个成绩单实例
0: 表示给三门课赋值
1: 将所有信息输出
2: 输出三门课中最高值
3: 输出三门课中最低值
4: 判断数学是否及格，若及格输出“yes”，否则输出“no”
5: 判断英语是否及格，若及格输出“yes”，否则输出“no”
6: 判断计算机是否及格，若及格输出“yes”，否则输出“no”



### 代码样例

```cpp
#include "class.h"
#include<cstring>

using namespace std;


PersonScore::PersonScore(char* i, char* n, int m, int e, int c) {
    // Your code goes here
    if(i!=NULL) strcpy(id,i);
    else strcpy(id,"00000000");
    if(n!=NULL) strcpy(name,n);
    else strcpy(name,"name");
    math = m;
    English = e;
    CS = c;
    
}

PersonScore::~PersonScore() {
    
}

void PersonScore::GiveValue(int m, int e, int c){
    // Your code goes here
    math = m;
    English = e;
    CS = c;
}

void PersonScore::Display(){
    // Your code goes here
    cout<<id<<" "<<name<<" "<<math<<" "<<English<<" "<<CS<<endl;
}

int PersonScore::GetHigh(){
    // Your code goes here
    int tmp = math;
    if(tmp<English) tmp=English;
    if(tmp<CS) tmp=CS;
    return tmp;
}

int PersonScore::GetLow(){
    // Your code goes here
    int tmp = math;
    if(tmp>English) tmp=English;
    if(tmp>CS) tmp=CS;
    return tmp;
}

bool PersonScore::isMathPass(){
    // Your code goes here
    if(math>=60) return true;
    else return false;
}

bool PersonScore::isEnglishPass(){
    // Your code goes here
    if(English>=60) return true;
    else return false;
}

bool PersonScore::isCSPass(){
    // Your code goes here
    if(CS>=60) return true;
    else return false;
}


```





## 10.1.2 任务名称

坐标点类

## Description

设计一个坐标类。

## Note
本题提供了main.cpp. class.h。你只需要编辑class.cpp，本题中不需要编辑其他文件。

## Input Format

输入
输入多个在[0, 9]中的数字（用数字代表所需操作），若相应操作需要值时，紧跟着输入, 用-1代表结束输入操作

## Output Format

输出
相应操作的输出


## Sample Input
```
0
2 23
3 34
0
4 45 67
0
5
1
6 87
7 89
9
0
-1
```

## Sample Output
```
0 0
23 34
45 67
45 67
87 89
```

## Explanation

解释
在输入操作数之前，需创建好了两个坐标点实例p，q
0：输出p坐标点横、纵坐标值，用空格隔开，换行结尾
1: 输出q坐标点横、纵坐标值，用空格隔开，换行结尾
2: 设定p的横坐标
3: 设定p的纵坐标
4: 设定p的横坐标及纵坐标
5: 将p的坐标值赋值给q
6: 设定q的横坐标
7: 设定q的纵坐标
8: 设定q的横坐标及纵坐标
9: 将q的坐标值赋值给p



### 代码样例

```cpp
#include "class.h"

// Your code goes here
Point::Point(double nx, double ny){
    x=nx;
    y=ny;
}
Point::Point(Point &np){
    x=np.x;
    y=np.y;
}
Point::~Point(){

}
void Point::SetX(double nx){
    x=nx;
}
void Point::SetY(double ny){
    y=ny;
}
void Point::SetPoint(double nx, double ny){
    x=nx;
    y=ny;
}
void Point::SetPoint(Point &np){
    x=np.x;
    y=np.y;
}

```





## 10.1.3 任务名称

温度计类

## Description
实现一个存储温度信息，且能够分别以摄氏和华氏形式显示的温度计类。
根据main函数的代码，补全class.cpp中的 ```//TODO``` 的内容 
输出

提示：$$华氏度 = 32°F+ 摄氏度 * 1.8$$

## Note
本题提供了main.cpp. class.h。你只需要编辑class.cpp，本题中不需要编辑其他文件。

## Input Format
第一行 T t : 表示操作的次数和温度计初始值（摄氏度）
第二行到第T+1行 每行有如下四种   
a t : 设置温度计值为t（摄氏度）  
b t : 设置温度计值为t（华氏度）  
c : 输出温度计值（摄氏度）  
d : 输出温度计值（华氏度）  
## Output Format
按照输入要求输出 保留两位小数
## Sample Input
```
5 37.5
c
d
a 100
d
b 100
c
```
## Sample Output
```
37.50
99.50
212.00
37.78
```

### 代码样例

```cpp
#include"class.h"
Thermometer::Thermometer(double temp){tempCelsius=temp;tempFahrenheit=temp*(1.8)+32;}

Thermometer::~Thermometer(){}

void Thermometer::SetTempCelsius(double tempC){tempCelsius=tempC;}

void Thermometer::SetTempFahrenheit(double tempF){tempFahrenheit=tempF;};

double Thermometer::GetTempCelsius(){return (tempFahrenheit-32)/1.8;}

double Thermometer::GetTempFahrenheit(){return tempCelsius*(1.8)+32;}
```





## 10.1.4 任务名称

时钟类

## Description
设计一个```hh:mm:ss```格式的时钟类，支持时间的修改和计算两个时间的差值(绝对值)  
使用给出的接口

## Note
本题需要你编辑main.cpp, class.h, class.cpp三个文件

## Input Format
输入两个时间 计算差值（两个时间不保证先后顺序）  
hh:mm:ss  
hh:mm:ss
## Output Format
时间的差值（绝对值）  
以hh:mm:ss的格式输出（注意前导0）
## Sample Input
```
10:30:25
14:20:34
```
## Sample Output
```
03:50:09
```

### 代码样例

```cpp
#include "class.h"
#include <iostream>
#include <cmath>

using namespace std;

Clock::Clock(char time[9])
{
	h = (time[0] - 48) * 10 + (time[1] - 48);
	m = (time[3] - 48) * 10 + (time[4] - 48);
	s = (time[6] - 48) * 10 + (time[7] - 48);
}

Clock::Clock()
{
	;
}

void Clock::Display()
{
	if (h < 10) {
		cout << '0' << h << ':';
	}
	else cout << h << ':'; 
	
	if (m < 10) {
		cout << '0' << m << ':';
	}
	else cout << m << ':';
	
	if (s < 10) {
		cout << '0' << s;
	}
	else cout << s << endl;
}

void Clock::MinusTime(const Clock& c1, const Clock& c2)
{
	int s1 = c1.h * 3600 + c1.m * 60 + c1.s;
	int s2 = c2.h * 3600 + c2.m * 60 + c2.s;
	int s3 = abs(s1 - s2);

	h = s3 / 3600;
	s3 = s3 % 3600;
	m = s3 / 60;
	s = s3 % 60;
}

```



## 10.1.5 任务名称

圆类

## Description
实现一个圆类，用**private**方式存储圆的位置和半径信息（浮点数）  
实现一个以两个圆类的对象为参数的**友元**函数判断两个圆是否有重叠部分（不包括相切）  
若有重叠，输出两圆公共弦的长度
## Input Format
R1 x1 y1  
R2 x2 y2
## Output Format
1. 若有重叠  
一个浮点数（保留两位小数）:两圆公共弦的长度  
1. 若没有重叠  
NO

## Sample Input
```
2.0 0.0 0.0
2.0 2.0 2.0
```
## Sample Output
```
2.83
```

### 代码样例

```cpp
#include "class.h"
#include <cmath>
#include <iostream>
#define PI 3.1416
using namespace std;

void Circle::create(float r,float x,float y){
    r1=r;x1=x;y1=y;
}
float Circle::check(Circle c){
    float dis=sqrt((c.x1-x1)*(c.x1-x1)+((c.y1-y1)*(c.y1-y1))),ret;
    if(dis>c.r1+r1)return 0;
    ret=sqrt((c.r1+r1+dis)*(c.r1+r1-dis)*(c.r1+dis-r1)*(r1+dis-c.r1))/dis;
    return ret;
}
Circle::Circle(){}
Circle::~Circle(){}
```





## 10.1.6 任务名称

矩形类

## Description
实现一个矩形类，用**private**方式存储矩形**左下**和**右上**两个端点的信息。  
要求实现以下功能：  
1. 以**成员函数**实现计算矩形对象自身面积  
2. 以**构造函数**实现矩形对象的构造
3. 以**友元函数**实现计算两个矩形对象相交得到的矩形对象（若两个矩形不相交，则返回一个私有数据为((0, 0), (0, 0))的零矩形  

## Input Format
以 x1 y1 x2 y2的形式输入两个矩形 
(输入保证$x1 < x2, y1 < y2$，即左下右上)

## Output Format
输出两个矩形自身的面积  
输出两个矩形重叠部分的面积  
(均保留两位小数)

## Sample Input
```
0.0 -5.0 2.0 0.0
1.5 -3.0 3.0 -1.0
```

## Sample Output
```
10.00
3.00
1.00
```

### 代码样例

```cpp
#include "class.h"
#include <iostream>
#include <cmath>
#include <iomanip>

using namespace std;

Rect::Rect(double x1, double y1, double x2, double y2)
{
	ldx = x1;
	ldy = y1;
	rux = x2;
	ruy = y2;
}

void Rect::Square()
{
	s = (rux - ldx) * (ruy - ldy);
	cout << setiosflags(ios::fixed) << setprecision(2) << s << endl;
}
```





## 10.2.1 任务名称

大整数类

## Description
要求实现BigInteger类  即能存储任意位数(不超过1000位)的非负整数  
以**私有成员**形式存储非负数(int数组)本身和总位数  
以**成员函数**形式从cin读入数据  
以**友元函数**形式实现两个正数的加法，返回一个非负数(也是BigInteger对象)(不超过1000位)

## Input Format
两行 不超过1000位的非负整数

## Output Format
一行 两个非负整数的和

## Sample Input
11111111111111111111111111111111111111111111111111111
99999999999999999999999999999999999999999999999999999

## Sample Output
111111111111111111111111111111111111111111111111111110

### 代码样例

```cpp

```





## 10.2.2 任务名称

复数类

## Description
实现一个存储复数(x + iy)的类 x与y为浮点数
要求实现
1. 复数类的构造
2. 复数的加法
3. 复数的减法
4. 复数的乘法
5. 复数的除法

## Note
本题需要你编辑main.cpp, class.h, class.cpp三个文件

## Input Format
以x y形式输入两个复数

## Output Format
依次输出复数的加法、减法、乘法、除法结果(保留两位小数)

## Sample Input
1.0 2.0  
2.0 3.0  

## Sample Output
3.00 5.00  
-1.00 -1.00
-4.00 7.00
0.62 0.08  

### 代码样例

```cpp

```





## 10.2.3 任务名称

矩阵类

## Description

编写一个简单的矩阵类Matrix，能实现mxn阶矩阵的初始化(Initialization)、转置(Transpose)并打印、以及方阵行列式(Determinant)的计算。依次输出转置矩阵，和行列式，如果没有行列式，输出字符@

## Note
本题需要你编辑main.cpp, class.h, class.cpp三个文件

## Hints

部分示例代码如下

```c++
class Matrix {
public:
    void Initialization () {
      
    }
  	void Transpose (){
      
    }
  	int Determinant (   ){
      return 0;
    }
};
```

请补齐完整代码。

## Input Format

第一行有两个整数，m，n 表示矩阵有m行，n列

接下来输入mxn个矩阵元素

## Sample Input 1

```
2 3
1 3 4
2 4 5
```

## Sample Output 1

```
1 2
3 4
4 5
@
```

## Sample Input 2

```
2 2
1 3
2 4
```

## Sample Output 2

```
1 2
3 4
-2
```



### 代码样例

```cpp


```





## 10.2.4 任务名称

wall类

## Description
本题你需要编写一个wall类。wall的属性有length和width（均为非负整数）。wall类还有一个静态成员变量。请根据class.h的描述来实现wall类以及主函数。

## Note
main.cpp中已经定义了三个wall变量以及一个大小为4的wall数组。

本题需要你编辑main.cpp中的空缺内容，以及class.cpp全部内容。

## Hints

部分示例代码如下

```c++
// declaration of wall
class  wall
{
    int  length;
    int  width;
    
    // extra_data初始值应为1
    static int  extra_data;
public:
    wall();
    
    // 修改wall的length和width属性
    void set(int new_length, int new_width);
    
    // 返回wall的面积
    int get_area();
    
    //返回extra_data的值并使其加一
    int get_extra();
};
```

## Input Description
总共七行，分别代表要设置的三个wall变量的length和width，以及wall数组的四个成员的length和width。

## Sample Input 1

```
15 20
20 25
30 35
10 10
20 20
30 30
40 40
```

## Sample Output 1

```
Area of the small wall is 300
Area of the medium wall is 500
Area of the large wall is 1050
An array of wall area 0 is 100
An array of wall area 1 is 400
An array of wall area 2 is 900
An array of wall area 3 is 1600
Extra data value is 1
New Extra data value is 2
New Extra data value is 3
New Extra data value is 4
New Extra data value is 5
```



### 代码样例

```cpp

```



## 10.2.5 任务名称

简易字符串类

## Description

尝试实现一个简单的string类，用来更方便地处理字符串。该类拥有两个字符串成员：字符串长度和字符串的内容。

要求可以实现：打印字符串，求字符串长度，求子字符串，在字符串的某个位置(前)添加一个字符，查找字符串中的某个字符第一次出现的位置（若无返回-1），删除字符串的某个位置上的字符等。

## Note
本题需要你编辑main.cpp, class.h, class.cpp三个文件

## Hints

部分示例代码如下

```c++
class String {
private:
  	char *myStr;
  	int myLen;
public:
  	// TO DO
   	// 默认构造函数
    String(char *myStr = NULL);
    // 复制构造函数
    String(String &str);
    // 析构函数
    ~String();

    // 0:获取字符串长度
    int length();
    // 1:求子字符串[start,end]
    String substr(int start, int end);
  	// 2:查找首次出现字符c的位置
  	int find_first_of(char c);
  	// 3:在index处添加字符c
  	void add_before(int index, char c);
  	// 4:删除某个位置上的字符
  	void delete_at (int index);
  	// 5:输出字符串
  	void printStr ();
};
```

请补齐完整代码。

## Input Format

第一行是初始字符串

之后若干行为调用函数表示序号，以及所需要的参数

最后一行为@

## Sample Input 1

```
Hello, world!
0
1 2 5 
2 o
3 6 u
4 0
5
@
```

## Sample Output 1

```
llo,
4
ello, uworld!
```


### 代码样例

```cpp

```





## 10.2.6 任务名称

罗马数字类

## Description

罗马数字包含以下七种字符: I， V， X， L，C，D 和 M。

| 字符 | 数值 |
| :--: | :--: |
|  I   |  1   |
|  V   |  5   |
|  X   |  10  |
|  L   |  50  |
|  C   | 100  |
|  D   | 500  |
|  M   | 1000 |

例如， 罗马数字 2 写做 II ，即为两个并列的 1。12 写做 XII ，即为 X + II 。 27 写做  XXVII, 即为 XX + V + II 。

通常情况下，罗马数字中小的数字在大的数字的右边。但也存在特例，例如 4 不写做 IIII，而是 IV。数字 1 在数字 5 的左边，所表示的数等于大数 5 减小数 1 得到的数值 4 。同样地，数字 9 表示为 IX。这个特殊的规则只适用于以下六种情况：

I 可以放在 V (5) 和 X (10) 的左边，来表示 4 和 9。
X 可以放在 L (50) 和 C (100) 的左边，来表示 40 和 90。 
C 可以放在 D (500) 和 M (1000) 的左边，来表示 400 和 900。
给定一个罗马数字，将其转换成整数。输入确保在 1 到 3999 的范围内。

请编写一个罗马数字与整数的类RomanWithInt，类中函数能实现罗马数字与整数的相互转化。

## Note
本题需要你编辑main.cpp, class.h, class.cpp三个文件

## Input Format

若干行罗马数字与整型数字，顺序不定，

最后一行为@

## Sample Input 1

```
MCMXCIV
58
III
@
```

## Sample Output 1

```
1994
LVIII
3
```



### 代码样例

```cpp

```





## 10.2.7 任务名称

约瑟夫环类

## Description

请设计并实现一个解决约瑟夫环问题的类Joseph，当需要解决一个n个人的约瑟夫环问题，同时能调整喊到数字m的人退出。

能实现两个功能：

1. 输出删除过程 
2. 输出最后一个人


## Note
本题需要你编辑main.cpp, class.h, class.cpp三个文件

## Input Format

整型数n 整型数m

## Output Format

第一行一个 整型数，表示最后一个人

第二行开始 输出删除过程，用空格分开，最后一个数字后无空格。

## Sample Input 1

```
6 4
```

## Sample Output 1

```
4 2 1 3 6
5
```

### 代码样例

```cpp

```



## 10.2.8 任务名称

简易加减表达式类

## Description
实现一个有记录功能的简易加减表达式类。该类可以实现加法和减法以及记录表达式。


## Note
本题只需要你编辑class.cpp。
请根据main.cpp和class.h来编写函数内容。
- print_value函数打印value值。
- print_total_expression函数打印总表达式。
- print_self_expression函数打印该Calculator自带的表达式。
- combine函数将传入的Calculator总表达式添加到this->total_expression后面，并且更新this->value的值。并且返回当前Calculator本身。

## Input Format
三行，分别代表三个算子。算子example：
`+5`
`-1000`
每个算子只包含1个运算符号和符号后面的整数。


## Sample Input 1

```
+5
-100
-1000
```

## Sample Output 1

```
+5
+5
value is 5

+5-100
+5
value is -95

value is -2095
+5-100-1000-1000
```


### 代码样例

```cpp

```







