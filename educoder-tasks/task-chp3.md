# 实训作业参考答案 —— 第三章 分支程序设计



## 3.1 任务名称

编写成绩转换程序

### 任务描述


本关任务：编写一个成绩转换程序，对于输入的成绩 n，转换规则如下：A档为 90-100，B 档是 80-89，C 档是 70-79，D 档是 60-69，E 档是 0-59。

注意：编程过程中，可以采用if 语句，嵌套 if 语句或 switch 语句实现。请分别尝试各种语句的用法。

### 测试说明

输入描述：一个正整数 n(0<=n<=100)。
输出描述：对应的等级，一个字符 x ∈{A,B,C,D,E}。

样例输入：100
样例输出：A
样例输入：85
样例输出：B
样例输入：70
样例输出：C
样例输入：66
样例输出：D
样例输入：30
样例输出：E

### 代码样例

```cpp
#include<iostream>
using namespace std;

int main() {

// 请在下方添加代码
/********** Begin *********/
    int a;
    cin>>a;
    if (a<=100 and a>=90){
        cout<<"A";
    }
    else if (a<=89 and a>=80){
        cout<<"B";
    }
    else if (a<=79 and a>=70){
        cout<<"C";
    }
    else if (a<=69 and a>=60){
        cout<<"D";
    }
    else{
        cout<<"E";
    }


/********** End **********/

	return 0;
}
```





## 3.2 任务名称

判断字母是元音字母还是辅音字母

### 任务描述


本关任务：编写一个程序，对于一个输入的字母 char，判断该字母是元音字母还是辅音字母。对于元音字母，输出一个字符串"vowel"，对于辅音字母，输出一个字符串"consonant"。要求用 if 语句或 switch 语句实现。

### 测试说明

输入描述：一个小写字母c(‘a’<=c<=’z’)。 
输出描述：输出一个代表元音字母或者辅音字母的字符串。

样例输入1：c
样例输出1：consonant

样例输入2：a
样例输出2：vowel

### 代码样例

```cpp
#include<iostream>
using namespace std;

int main() {

// 请在下方添加代码
/********** Begin *********/
   char vowel[] = "aeiou";
   char a;
   cin>>a;
   for (int i=0;i<=4;i++){
   		if (a==vowel[i]){
   				cout<<"vowel";
   				return 0;
		   }
   }
   cout<<"consonant";


/********** End **********/

	return 0;
}
```




## 3.3 任务名称

排序

### 任务描述


本关任务：输入三个整数，a，b，c（均在 int 范围内），要求将这三个数从小到大排序输出。


### 测试说明

输入描述：三个整数 a，b，c，使用一个空格分隔。 
输出描述：三个从小到大排序后的整数，以空格分隔

样例输入1：73 114 5
样例输出1：5 73 114

样例输入2：100 100 50
样例输出2：50 100 100

### 代码样例

```cpp
// 请在下方添加代码
/********** Begin *********/
#include<iostream>

using namespace std;
int main() 
{
int a,b,c;
cin>>a>>b>>c;
if (a>=b and a>=c){
    if (b>=c){
        cout<<c<<" "<<b<<" "<<a;
    }else{
        cout<<b<<" "<<c<<" "<<a;
    }
}
else if (b>=a and b>=c){
    if (a>=c){
        cout<<c<<" "<<a<<" "<<b;
    }else{
        cout<<a<<" "<<c<<" "<<b;
    }
}
else if (c>=b and c>=a){
    if (b>=a){
        cout<<a<<" "<<b<<" "<<c;
    }else{
        cout<<b<<" "<<a<<" "<<c;
    }
}
else {
    cout<<a<<" "<<b<<" "<<c;
}
  return 0;
}
/********** End **********/
```



## 3.4 任务名称

判断回文数

### 任务描述


本关任务：所谓“回文”是一种特殊的或者文字短语。它们无论是顺读还是倒读，结果都是一样。例如，以下的几个 5 位整数都是回文数：12321、77777、89998 和 44774。编写一个程序，读入一个 5 位整数后，判断它是否是回文数。

### 测试说明

输入描述：一个 5 位整数
输出描述：“Yes”或“No”

样例输入1：12321
样例输出1：Yes
样例输入2：12323
样例输出2：No

### 代码样例

```cpp
#include <iostream>
using namespace std;

int main(void) {
/******** Begin ********/
    int n; cin >> n;
    if (n/10000 == n%10 && n/1000%10 == n/10%10)
        cout << "Yes" << endl;
    else cout << "No" << endl;

/********  End  ********/
    return 0;
}
```



## 3.5 任务名称

字符转换

### 任务描述


本关任务：从键盘输入一个字符，如果是大写字母，就转换为小写；如果是小写字母，就转换成大写，如果是其他字符就保持原样输出。

### 测试说明

输入描述：用键盘输入一个任意字符 
输出描述：输出转换后的字符

样例输入1：A
样例输出1：a

样例输入2：b
样例输出2：B

样例输入3：0
样例输出3：0

### 代码样例

```cpp
// 请在下方添加代码
/********** Begin *********/
#include<iostream>

using namespace std;
int main() 
{
char c;
cin>>c;
if (c<=90 and c>=65){
    cout<<char(c+32);
}else if (c>=97 and c<=122){
    cout<<char(c-32);
}else{
    cout<<c;
}
  return 0;
}
/********** End **********/
```




## 3.6 任务名称

停车收费系统

### 任务描述


本关任务：设计一停车场的收费系统。停车场有 3 类汽车，分别用 3 个字母表示。C 代表轿车，B 代表客车，T 代表卡车。收费标准如下：

| 车辆类型 | 收费标准                                      |
| -------- | --------------------------------------------- |
| 轿车(c)  | 三小时内，每小时5元。三小时后，每小时10元。   |
| 客车(b)  | 两小时内，每小时10 元。两小时后，每小时15元。 |
| 卡车(t)  | 一小时内，每小时10元，一小时后，每小时15元。  |


### 测试说明

输入描述：汽车类型(c/b/t)、入库时间（自然数）和出库时间（自然数）
输出描述：应交的停车费

样例输入1：b 7 9
样例输出1：20

样例输入2：c 6 11
样例输出2：35

### 代码样例

```cpp
// 请在下方添加代码
/********** Begin *********/
#include<iostream>

using namespace std;
int main() 
{

char t;
int a,b;
cin>>t>>a>>b;

int s = b-a;

if (t=='c'){
    if (s<=3){
        cout<<s*5;
    }else{
        cout<<(s-3)*10+15;
    }
}else if (t == 'b'){
    if (s<=2){
        cout<<s*10;
    }else{
        cout<<(s-2)*15+20;
    }
}else if (t == 't'){
    if (s<=1){
        cout<<s*10;
    }else{
        cout<<(s-1)*15+10;
    }
}
  return 0;
}
/********** End **********/

```



## 3.7 任务名称

第几天

### 任务描述


本关任务：输入三个正整数year、month、day分别表示年、月、日。假设输入总是合法日期，按以下步骤计算dayNum表示此日期为该年的第几天：1）dayNum=31(month-1)+day；2）二月以后的日期需要减去(4month+23)/10；3）如果是闰年则二月以后的日期需要再加1。


### 测试说明

输入描述：三个正整数year、month、day，用空格分开。 
输出描述：一个正整数，表示此日期为该年的第几天。

样例输入：2020 9 20
样例输出：264

### 代码样例

```cpp
#include <iostream>
using  namespace std;
int main()
{
    int year,month,day,dayNum;
    cin>>year;
    cout<<" ";
    cin>>month;
    cout<<" ";
    cin>>day;
    if (month<=2)
    dayNum=31*(month-1)+day;
    else {
        if (year%4!=0||(year%100==0&&year/100%4!=0))
           dayNum=31*(month-1)+day-(4*month+23)/10;
        else 
           dayNum=31*(month-1)+day-(4*month+23)/10+1;
    }
    cout <<dayNum;
    return 0;
}
```



## 3.8 任务名称

高度是多少

### 任务描述


本关任务：有4个圆塔，圆心坐标分别为(2,2)，(-2,2)，(-2,-2)和(2,-2)，半径均为1米，高度都是10米，塔以外无其它建筑物。现输入某个点的坐标，求该点的建筑高度（塔外的高度为0)。


### 测试说明

输入描述：点的坐标x和y。 
输出描述：点的高度。

样例输入：0.5 0.7
样例输出：0


### 代码样例

```cpp
#include <iostream>
using  namespace std;
int main()
{
    double x,y;
    cin>>x>>y;

    if ((x-2)*(x-2)+(y-2)*(y-2)<=1 || (x+2)*(x+2)+(y-2)*(y-2)<=1 || (x-2)*(x-2)+(y+2)*(y+2)<=1 || (x+2)*(x+2)+(y+2)*(y+2)<=1) 
    cout<<10<<endl;
    else cout<<0<<endl;


    return 0;
}
```





## 3.9 任务名称

乒乓球比赛

### 任务描述


本关任务：编写程序判断乒乓球比赛的结果：输入双方比分（两个非负整数），输出谁胜谁负，注意，输入的可能是一局比赛结束时的比分，也可能是比赛进行过程中的比分，还有可能是非法比分

### 测试说明

输入描述：两个非负整数 a，b，使用一个空格分隔。
输出描述：”A win”, “B win”, “In progress”, “Illegal”。

样例输入1：11 4
样例输出1：A win

样例输入2：18 9
样例输出2：Illegal

### 代码样例

```cpp
#include <iostream>
using  namespace std;
int main()
{
    int a,b;
    cin>>a>>b;
    
    if ((a-2>=b && a==11) || (a-2==b && a>11)) cout<<"A win"<<endl;
    else if ((b-2>=a && b==11) || (b-2==a && b>11)) cout<<"B win"<<endl;
    else if ((a-2>b && a>11)||(b-2>a && b>11)) cout<<"Illegal"<<endl;
    else cout<<"In progress"<<endl;

    return 0;
}
```




## 3.10 任务名称

三角形判别

### 任务描述


本关任务：用户输入三个正整数，判别这三个数能否构成一个三角形，如果是三角形的话再判别是否是一个直角三角形。


### 测试说明

输入描述：输入三个正整数，使用空格分隔。
输出描述：判别结果。

样例输入1：1 2 3
样例输出1：no

样例输入2：3 4 5
样例输出2: yes yes

样例输入3：3 4 6
样例输出3: yes no


### 代码样例

```cpp  //by 王一舟
#include <iostream>
using  namespace std;
int main()
{
    int a,b,c,x;
    cin>>a>>b>>c;

    if (c>b) x=c, c=b, b=x;
    if (b>a) x=b, b=a, a=x;

    if (a>=b+c) cout<<"no"<<endl;
        else  {
            cout<<"yes"<<endl;
    if (a*a==b*b+c*c) cout<<"yes"<<endl;
        else cout<<"no"<<endl;
        }
    return 0;
}
```



## 3.11 任务名称

鸡兔同笼

### 任务描述


本关任务：已知鸡和兔的总数量为n，腿的总数量为m，求鸡和兔的数量


### 测试说明

输入描述：两个正整数n和m，用一个空格分开。 
输出描述：鸡和兔的数目。

样例输入1：14 32
样例输出1：12 2

样例输入2：10 16
样例输出2：no solution

### 代码样例

```cpp  //by 林袁艺
#include <iostream>
using  namespace std;
int main()
{
    int head,foot;
    int chicken,rabit;

    cin>>head>>foot;

    if (foot%2==1) {cout<<"no solution"<<endl;}
    else
    {
        chicken=2*head-foot/2;
        rabit=foot/2-head;
        if (chicken<=0 ||rabit<=0) {cout<<"no solution"<<endl;}
        else
        {
            cout<<chicken<<" "<<rabit<<endl;
        }

    }
    return 0;
}
```


## 3.12 任务名称

第几天(2)

### 任务描述


本关任务：输入三个正整数month、day、year分别表示月、日、年。首先检验输入是否表示一个合法的日期，如果是合法日期则按以下步骤计算dayNum表示此日期为该年的第几天：1）dayNum=31(month-1)+day；2）二月以后的日期需要减去(4month+23)/10；3）如果是闰年则二月以后的日期需要再加1。假设输入总是正整数


### 测试说明

输入描述：输入三个正整数year、month、day，用空格分开。
输出描述：一个正整数，表示此日期为该年的第几天，或者输出Illegal，表示不是一个合法的日期。

样例输入1：2020 9 20
样例输出1：264

样例输入2：2100 2 29
样例输出2：Illegal

### 代码样例

```cpp //by 林袁艺
#include <iostream>
using  namespace std;
int main()
{
    int year,month,day,daynum=0;
    bool yearflag,flag=false; //yearflag=true 表示是闰年 flag=false 表示合法

    cin>>year>>month>>day;

    //检验是否合法
    if (year<=0) {flag=true;}
    if (!flag) {yearflag=((year%4==0)&&(year%100!=0))||(year%400==0);}
    if (!flag&&(month<=0||month>=13)) {flag=true;}
    if (!flag&&(day<=0||day>=32)) {flag=true;}
    if (!flag)
    {
            switch (month)
            {
              case 2:
                   if (yearflag)
                   {
                       if (day>=30) {flag=true;}
                   }
                   else
                   {
                       if (day>=29) {flag=true;}
                   }
                   break;
              case 4:
              case 6:
              case 9:
              case 11:
                   if (day==31) {flag=true;}
           }
    }
    //计算第几天
    if (!flag)
        {daynum=31*(month-1)+day;
        if (month>2) {daynum-=(4*month+23)/10;}
        if (yearflag && month>2) {daynum++;}

        cout<<daynum<<endl;}
    else
    {
        cout<<"Illegal"<<endl;
    }
    return 0;
}
```




## 3.13 任务名称

加法

### 任务描述


本关任务：编写一个能计算两整数之和的小程序。


### 测试说明

输入描述：输入两个int型整数。
输出描述：输出和，如有溢出则发出提示信息。

样例输入1：1 1
样例输出1：2

样例输入2：1234567890 987654321
样例输出2：error

### 代码样例

```cpp  //by 辛统
#include <iostream>
#include <bits/stdc++.h>
using namespace std;
int main() {
    int a, b, c;
    cin >> a >>b;
    c = a + b;
    if((a > 0 && b > 0 && c <= 0) || (a < 0 && b < 0 && c >= 0)) {
        puts("error");
    }
    else cout<<a+b;
}

```








