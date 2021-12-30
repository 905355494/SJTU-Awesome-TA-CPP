# 实训作业参考答案 —— 第十章 类(上、下)



## 10.1.1 圆

### 任务描述


本关任务：定义圆的类Circle，包含三个属性：圆心(x,y)和半径r

### 编程要求

根据提示，在右侧编辑器补充代码，定义圆的类Circle，包含三个属性：圆心(x,y)和半径r，成员函数见main函数。用户先输入整数x, y, r，表示圆心（x,y）和半径r，程序输出圆的圆心坐标，以及圆的半径。用户再输入整数move_x, move_y，表示圆心的偏移量。程序输出移动后的圆的圆心坐标。用户最后输入整数new_r，表示新的半径，程序输出修改后的圆的半径。


### 测试说明

平台会对你编写的代码进行测试：

测试输入：
`2 3 5`
`-1 1`
`10`

预期输出：
`2 3`
`5`
`1 4`
`10`

### 代码样例

```cpp
// circle.cpp


// circle.h
class Circle{
      int x,y,r;
      public:
      Circle(int a, int b, int c):x(a),y(b),r(c){}
      void getO(int &a, int &b){a=x;b=y;};
      int getR(){return r;}
      void move(int a, int b){x+=a;y+=b;}
      void setR(int c){r=c;}
  };


// main.cpp
#include "circle.h"
#include <iostream>
using namespace std;
int main()
{
    int x,y,r;
    cin>>x>>y>>r;
    Circle c(x,y,r);

    int cx,cy;
    c.getO(cx,cy);
    cout<<cx<<' '<<cy<<endl;
    cout<<c.getR()<<endl;

    int move_x,move_y;
    cin>>move_x>>move_y;
    c.move(move_x,move_y);  
    c.getO(cx,cy);
    cout<<cx<<' '<<cy<<endl;

    int new_r;
    cin>>new_r;
    c.setR(new_r);
    cout<<c.getR()<<endl;

    return 0;
}   
```



## 10.1.2 银行账户

### 任务描述


本关任务：定义账户类SavingAccount，包含账号，存款金额和月利率。

### 编程要求

根据提示，在右侧编辑器补充代码，要求账号自动生成，第一个生成的对象账号为1，第二个生成的对象账号为2，依此类推。所需的操作包括修改月利率，每月计算新的存款额（原金额加上本月利息）和显示账户金额。不得使用全局变量。月利率初始值为0.05。本题已给定main()函数，输入共三次：第一次是第一个账户和第二个账户的存款金额；第二次是第二个月以后新的月利率；第三次是第三个账户的存款金额。输出是四个月的所有账户的账号、存款金额和月利率。(存款金额四舍五入保留两位小数)

### 测试说明

平台会对你编写的代码进行测试：

测试输入：
`20000 10000`
`0.01`
`30000`

预期输出：
`1 20000.00 0.05`
`2 10000.00 0.05`
`1 21000.00 0.05`
`2 10500.00 0.05`
`1 21210.00 0.01`
`2 10605.00 0.01`
`1 21422.10 0.01`
`2 10711.05 0.01`
`3 31500.00 0.05`

### 代码样例

```cpp
// account.cpp
#include "account.h"
//float SavingAccount::rate=0.05;
int SavingAccount::num=0;

// account.h
#include<iostream>
#include<iomanip>
using namespace std;
 class SavingAccount{
     int ID;
     double deposit;
     float rate;
     static int num;
     public:
     SavingAccount(double d):deposit(d){num++;ID=num;rate=0.05;}
     void display(){cout<<fixed<<setprecision(2)<<ID<<' '<<deposit<<' '<<rate<<endl;}
     void calculate(){deposit*=(1+rate);}
     void changerate(float n_rate){rate=n_rate;}
 };

// main.cpp
#include "account.h"
#include <iostream>
using namespace std;

int main()
{
    // 1st month
    int first_money, second_money;
    cin>>first_money>>second_money;
    SavingAccount first(first_money);
    SavingAccount second(second_money);
    first.display();
    second.display();

    // 2nd month
    float new_rate;
    cin>>new_rate;
    first.calculate();
    first.display();
    second.calculate();
    second.display();
    first.changerate(new_rate);
    second.changerate(new_rate);

    // 3rd month
    int third_money;
    cin>>third_money;
    first.calculate();
    first.display();
    second.calculate();
    second.display();
    SavingAccount * p = new SavingAccount(third_money);

    // 4th month
    first.calculate();
    first.display();
    second.calculate();
    second.display();
    p->calculate();
    p->display();

    delete p;
    return 0;
}
```



## 10.2.1 LongLongInt

### 任务描述


本关任务：定义可处理任意大的正整数类LongLongInt

### 编程要求

根据提示，在右侧编辑器补充代码，定义可处理任意大的正整数类LongLongInt，用一个动态字符数组存放任意长度的正整数，数组的每个元素存放整型数的一位。用户输入两个任意长度的正整数，输出这两个数的和。

### 测试说明

平台会对你编写的代码进行测试：

测试输入：
`9934`
`567`

预期输出：
`10501`

### 代码样例

```cpp
// LongLongInt.cpp
#include "LongLongInt.h"
bigInt &sum(bigInt &a, bigInt &b){
    bigInt *s=new bigInt;
    int i,j=0;
    for(i=0;i<1000;i++){
        s->s[i]=a.s[i]-'0'+b.s[i]-'0'+j;
        if(s->s[i]>=10)j=s->s[i]/10;else j=0;
        s->s[i]=s->s[i]%10+'0';
    }
    return *s;
}

// LongLongInt.h
#include<iostream>
#include<cstring>
using namespace std;
 class bigInt{
     friend bigInt &sum(bigInt &a, bigInt &b);
     char * s;
     public:
     bigInt(){s=new char[1000];}
     bigInt(const bigInt &bi){
         s=new char[1000];
         int i=0;
         while(bi.s[i]){
             s[i]=bi.s[i];
             i++;
         }
         s[i]=0;
     }
     void read(){
         char st[1000];
         int n=0;
         cin.getline(st,1000);
         int l=strlen(st)-1;
         while(l>=0){
             s[n]=st[l];
             n++;l--;
         }
         for(;n<1000;n++){
         s[n]='0';}
         }
     void show(){
         int i=1000-1;
         while(s[i]=='0')i--;
         while(i>=0){
             cout<<s[i];
             i--;
         }
         cout<<endl;
     }
 };

// main.cpp
#include <iostream>
#include "LongLongInt.h"

using namespace std;

int main(){

    bigInt x1;
    bigInt x2;
    x1.read();
    x2.read();
    sum(x1,x2).show();
    return 0;
}
```



## 10.2.2 时钟

### 任务描述

本关任务：设计一个```hh:mm:ss```格式的时钟类，支持时间的修改和计算两个时间的差值(后者减前者的绝对值) 

### 编程要求

根据提示，在右侧编辑器补充代码，完成时钟类的定义。用户输入两个时间（24小时制），计算其差值（两个时间不保证先后顺序）  

### 测试说明

平台会对你编写的代码进行测试：

测试输入：
`10:30:25`
`14:20:34`

预期输出：
`03:50:09`

### 代码样例

```cpp
// clock.cpp



// clock.h
#include<iostream>
using namespace std;
 class clockn{
     int h,m,s;
     public:
     void input(){
         char c[9]={0};
         cin.getline(c,9);
         if(c[0]=='0')h=c[1]-'0';else {h=c[0]-'0'; h=10*h+c[1]-'0';}
         if(c[3]=='0')m=c[4]-'0';else {m=c[3]-'0'; m=10*m+c[4]-'0';}
         if(c[6]=='0')s=c[7]-'0';else {s=c[6]-'0'; s=10*s+c[7]-'0';}
     }
     void sub_in(clockn &a, clockn &b){
         int j=0;
         if(a.s>b.s){s=a.s-b.s;j=0;}else{a.s+60-b.s;j=1;}
         if(a.m-j>b.m){m=a.m-j-b.m;j=0;}else{m=a.m-j+60-b.m;j=1;}
         h=a.h-j-b.h;
     }
     void sub(clockn &a, clockn &b){
         bool flag;
         if(a.h>b.h){flag=true;}
         else if(a.h<b.h){flag=false;}
         else if(a.m>b.m){flag=true;}
         else if(a.m<b.m){flag=false;}
         else if(a.s>b.s){flag=true;}
         else if(a.s<b.s){flag=false;}
         else{h=0;m=0;s=0;}
         if(flag)sub_in(a,b);
         else sub_in(b,a);
     }
     void show(){
         char c[9]="00:00:00";
         c[0]=h/10+'0';
         c[1]=h%10+'0';
         c[3]=m/10+'0';
         c[4]=m%10+'0';
         c[6]=s/10+'0';
         c[7]=s%10+'0';
         cout<<c<<endl;
     }
 };

// main.cpp
#include <iostream>
#include "clock.h"
using namespace std;

int main() {
    clockn a,b,c;
    a.input();
    b.input();
    c.sub(a,b);
    c.show();

    return 0;
}
```



## 10.3.1 简易字符串类

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
// class.cpp
#include "class.h"


// class.h
#ifndef CLASS_H
#define CLASS_H
#include<cstring>
using namespace std;
class String {
private:
      char *myStr;
      int myLen;
public:
      // TO DO
       // 默认构造函数
    String(char *Str = NULL){
        if(Str){
            mylen=strlen(Str);
            myStr=new char[mylen+1];
            strcpy(myStr,Str);
        }
    }
    // 复制构造函数
    String(const String &str){
        
    }
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

#endif /* CLASS_H */


// main.cpp
#include <iostream>
#include "class.h"

using namespace std;

int main(){
    char s[100];
    cin.getline(s,100);
    String st(s);
    char c;
    int l,i,x,y;
    char ch;
    bool flag=true;
    while(flag){
        //cin.ignore();
        cin>>c;
        switch(c){
            case '0': l=st.length();break;
            case '1': cin>>x>>y; st.substr(x, y).printStr();break;
            case '2': cin>>ch; cout<<st.find_first_of(ch)<<endl;break;
            case '3': cin>>i;cin>>ch; st.add_before(i, ch); break;
            case '4': cin>>i; st.delete_at(i);break;
            case '5': st.printStr();break;
            case '@': flag=false;break;
        }
    }
    return 0;
}
```



## 10.3.2 罗马数字类

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
// class.cpp



// class.h
#ifndef CLASS_H
#define CLASS_H
#include<cstring>
#include<iostream>
using namespace std;
char rom[7]={'I','V','X','L','C','D','M'};
class RomanWithInt{
    char st[50];
    public:
    int dt(char c){
        switch(c){
            case 'I': return 1;
            case 'V': return 5;
            case 'X': return 10;
            case 'L': return 50;
            case 'C': return 100;
            case 'D': return 500;
            case 'M': return 1000;
        }
    }
    void i2r(char * ch){
        char s[50];
        int l = strlen(ch);
        int j=0, d=0;
        for(int i=l-1;i>=0;i--){
            int k = ch[i]-'0';
            int m=k%5;
            if(m==4){if(k/5){s[j++]=rom[2*(d+1)];}else{s[j++]=rom[2*d+1];}s[j++]=rom[2*d];}
            else{
                while(m--){
                    s[j++]=rom[2*d];
                }
                if(k/5)s[j++]=rom[2*d+1];
            } 
            d++;
        }
        for(int n=0;n<j;n++){
            st[n]=s[j-n-1];
        }
        st[j]=0;
    }
    void r2i(char *ch){
        int s=0;
        int l = strlen(ch);
        for(int i=l-1;i>=0;i--){
            if(i==l-1)
                s+=dt(ch[i]);
            else
                if(dt(ch[i])<dt(ch[i+1])){
                    s-=dt(ch[i]);
                }
                else
                    s+=dt(ch[i]);
        }
        int j=0;
        while(s){
            st[j++]=s%10+'0';
            s=s/10;
        }
        char tmp;
        for(int k=0;k<j/2;k++){
            tmp = st[k];
            st[k] = st[j-k-1];
            st[j-k-1] = tmp;
        }
        st[j]=0;
    }
    void show(){
        cout<<st<<endl;
    }
};

#endif /* CLASS_H */


// main.cpp
#include <iostream>
#include "class.h"

using namespace std;

int main(){

    RomanWithInt ri;
    char ch[50];
    while(true){
        cin.getline(ch,50);
        if(ch[0]=='@')break;
        if(ch[0]>='0'&&ch[0]<='9'){
            ri.i2r(ch);
            //ri.show();
        }
        else{
            ri.r2i(ch);
        }
        ri.show();
    }
    return 0;
}
```



## 10.3.3 约瑟夫环类

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
// class.cpp
#include "class.h"


// class.h
#ifndef CLASS_H
#define CLASS_H
#include <iostream>
using namespace std;

class Joseph{
    int n,m;
    int l;
    public:
    Joseph(int a, int b):n(a),m(b){}
    void run(){
        int *arr = new int[n];
        int *p = arr;
        int c=0;
        for(int i=0; i<n; i++)arr[i]=1;
        int j=n-1;
        while(j--){
            if(j!=n-2)cout<<' ';
            for(int i=0; i<m-1; i++){
                while(*p==0){p++;c++;if(c==n){p=arr;c=0;}}
                {p++;c++;if(c==n){p=arr;c=0;}}
            }
            while(*p==0){p++;c++;if(c==n){p=arr;c=0;}}
            *p=0;
            cout<<c+1;
            {p++;c++;if(c==n){p=arr;c=0;}}
        }
        for(int i=0; i<n; i++){
            if(arr[i]==1){l=i+1;break;}
        }
        cout<<endl;
        delete arr;

    }
    void last(){
        cout<<l;
    }
};

#endif /* CLASS_H */

// main.cpp
#include <iostream>
#include "class.h"

using namespace std;

int main(){

    int n,m;
    cin>>n>>m;
    Joseph J(n,m);
    J.run();
    J.last();

    return 0;
}
```



## 10.3.4 简易加减表达式类

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
// class.cpp
#include "class.h"

Calculator::Calculator(const char* expr){
    int l=strlen(expr);
    self_expression = new char[l+1];
    total_expression = new char[l+1];
    strcpy(self_expression,expr);
    strcpy(total_expression,expr);
    value=0;
    for(int i=1;i<l;i++){
        value=10*value+expr[i]-'0';
    }
    if(expr[0]=='-')value=-value;
}

Calculator::~Calculator(){
    delete self_expression;
    delete total_expression;
}

Calculator & Calculator::combine(const Calculator & sa){
    int l = strlen(total_expression)+strlen(sa.total_expression);
    char *p= new char[l+1];
    strcat(p,total_expression);
    strcat(p,sa.total_expression);
    delete total_expression;
    total_expression=p;
    value+=sa.value;
    return *this;
}
void Calculator::print_value() const{
    cout<<"value is "<<value<<endl;
}
void Calculator::print_total_expression() const{
    cout<<total_expression<<endl;
}
void Calculator::print_self_expression() const{
    cout<<self_expression<<endl;
}


// class.h
#ifndef CLASS_H
#define CLASS_H

#include<iostream>
#include<cstring>
using namespace std;

struct Calculator
{
private:
    char* self_expression;
    char* total_expression;
    int value;
public:
    Calculator(const char* expr);
    ~Calculator();
    Calculator & combine(const Calculator & sa);
    void print_value() const;
    void print_total_expression() const;
    void print_self_expression() const;
};

#endif // CLASS_H


// main.cpp
#include<iostream>
#include "class.h"

using namespace std;

int main(){
    char str1[10];
    char str2[10];
    char str3[10];
    cin>>str1>>str2>>str3;

    Calculator c1(str1);
    Calculator c2(str2);
    Calculator c3(str3);

    c1.print_total_expression();
    c1.print_self_expression();
    c1.print_value();

    cout<<endl;

    c1.combine(c2);
    c1.print_total_expression();
    c1.print_self_expression();
    c1.print_value();
    cout<<endl;

    c1.combine(c3).combine(c3).print_value();
    c1.print_total_expression();
    cout<<endl;

    return 0;
}
```



## 10.5.1 栈

### 任务描述


本关任务：栈是一种只能在一端进行插入和删除操作的数据结构，按照先进后出的原则存储数据，先进入的数据被压入栈底，最后的数据在栈顶，需要读数据的时候从栈顶开始弹出数据（最后一个数据被第一个读出来）。定义栈类mystack，用一个动态整型数组存放栈的数据，数据成员包括指向动态数组的指针，栈的最大规模（缺省值为100）和栈顶指针，要求能够判别栈满和栈空，数据进栈函数push，出栈函数pop等。

### 编程要求

根据提示，在右侧编辑器补充代码，main()函数已隐藏以避免被修改，内容如下：

int main()
{
    int num[]={1,3,5,7,9,11},i,data;
    mystack s(5);
    cout<<"The stack is empty: "<<s.isempty()<<endl;
    cout<<"The stack is full: "<<s.isfull()<<endl;
    for(i=0;i<=5;i++)
    {
        if(s.push(num[i]))
            cout<<"Push "<<num[i]<<" success!"<<endl;
        else
            cout<<"Push "<<num[i]<<" fail!"<<endl;
    }
    cout<<"The stack is empty: "<<s.isempty()<<endl;
    cout<<"The stack is full: "<<s.isfull()<<endl;
    for(i=0;i<=5;i++)
    {
        if(s.pop(data))
            cout<<"Pop "<<data<<" success!"<<endl;
        else
            cout<<"Pop fail!"<<endl;
    }
    return 0;
}
请从给出的main()函数推断出要实现的功能和函数。给出的main()函数不一定代表真实的测试程序的方式。

### 测试说明

平台会对你编写的代码进行测试：
对应于所给main函数，其输出为：
The stack is empty: 1
The stack is full: 0
Push 1 success!
Push 3 success!
Push 5 success!
Push 7 success!
Push 9 success!
Push 11 fail!
The stack is empty: 0
The stack is full: 1
Pop 9 success!
Pop 7 success!
Pop 5 success!
Pop 3 success!
Pop 1 success!
Pop fail!

### 代码样例(By 盛玉磊)

```cpp
// mystack.cpp
#include <iostream>
#include "mystack.h"
using namespace std;
mystack::mystack(int num=100)
{
    pointer=new int [num];    
    upOfStack=pointer-1;
    Size=num;
}
bool mystack::isempty()
{
    if (upOfStack==(pointer-1))
    {
        return true;
    }
    else return false;
}
bool mystack::isfull()
{
    if (upOfStack-pointer==(Size-1))
    {
        return true;
    }
    else return false;
}
bool mystack::push(int i)
{
    if (upOfStack-pointer<(Size-1))
    {   upOfStack++;
        *upOfStack=i;
        return true;
    }
    else return false;
}
bool mystack::pop(int &data)
{
    if (upOfStack>=pointer)
    {
        data=*upOfStack;
        upOfStack--;
        return true;
    }
    else return false;
}


// mystack.h
#ifndef MYSTACK
#define MYSTACK
class mystack
{
    int *pointer;
    int *upOfStack;
    int Size;
public:
    mystack (int num);
    bool  isempty ();
    bool  isfull();
    bool push (int i);
    bool pop (int &data);
    ~mystack()
    {
        if (pointer)
        {
            delete []pointer;
            upOfStack=pointer=NULL;
            Size=0;
        }
    }
};
#endif // MYSTACK
```

