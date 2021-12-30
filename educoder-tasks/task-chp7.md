# 实训作业参考答案 —— 第七章 指针（上、下）



## 7.1.1 变换单词顺序

### 任务描述

设计一个程序，让用户输入一行句子，数出句子中有多少个单词并输出，再让用户输入一串数字表示单词重新排序的顺序，最后按用户设定的顺序来输出一行新的句子。要求所有数组都只能用new来定义。


### 说明

1. 用户输入的句子里只包含字母和空格（句子末尾没有空格），以回车完成输入，该句子最多100个字符，句子里最多10个单词。
2. 用户输入的一串数字是正常表示单词顺序的，不用考虑异常情况。


为了完成本关任务，你需要掌握：1.如何获取数组的长度，2.如何遍历数组。

### 输入输出样例

样例1
Input: `This is a good day to work`
Output: `7`
Input: `6543210`
Output: `work to day good a is This`

样例2
Input: `Welcome to my hometown`
Output: `4`
Input: `1302`
Output: `to hometown Welcome my`

### 代码样例

```cpp
#include <iostream>
using namespace std;

int main()
{    
    char sentence[101];
    char order[11];
    char *s=sentence;
    char *o=order;
    int i=0;
    cin.getline(s,101);
    cin.getline(order,11);
    char *word[11];
    while(*s){
        while(*s==' ')s++;
        word[i]=new char[101];
        char *p=word[i];
        while(*s!=' '&&*s!=0){
            *p=*s;
            p++;s++;
        }
        *p=0;
        i++;
    }
    cout<<i<<endl;
    while(*o){
        cout<<word[*o-'0']<<' ';
        delete word[*o-'0'];
        o++; 
    }
    return 0;
}
```



## 7.1.2 约瑟夫环问题

### 任务描述

n个人围成一圈，按顺序从1到n编号。从第一个人开始报数1、2、3，报到3的人退出圈子，下一个人从1开始重新报数，报到3的人退出圈子。如此进行下去，直到留下最后一个人。当给定一个正整数n时，请问留下来的人的编号是多少？

### 输入输出示例

input:`4`
output:`1`

### 代码样例

```cpp
#include <iostream>
using namespace std;

int main()
{    
    int n;
    cin>>n;
    int *arr = new int[n];
    int *p = arr;
    int c=0;
    for(int i=0; i<n; i++)arr[i]=1;
    int j=n-1;
    while(j--){
        for(int i=0; i<2; i++){
            while(*p==0){p++;c++;if(c==n){p=arr;c=0;}}
            {p++;c++;if(c==n){p=arr;c=0;}}
        }
        while(*p==0){p++;c++;if(c==n){p=arr;c=0;}}
        *p=0;
        {p++;c++;if(c==n){p=arr;c=0;}}
    }
    for(int i=0; i<n; i++){
        if(arr[i]==1){cout<<i+1;break;}
    }
    delete arr;

    return 0;
}
```



## 7.1.3 再次判断回文数

### 任务描述


本关任务：把右侧代码中的两个函数main和func填补完整，使得该程序能判断用户输入的一个正整数是否为回文数（即顺读和倒读相同的数）。

### 说明

1：只能在“此处填补几行代码”的位置添加代码。
2：不可定义新的变量、数组或其它对象。不可使用循环。
3：func函数的定义中不可调用库函数。
4：用户的输入必定为一串数字（少于20个字符），以回车完成输入。
5：填补部分的代码总共不超过10行（分号和逗号合计不超过10个）。

### 输入输出样例

样例1. input:`338909833`
output:`Yes`

样例2. input:`378909833`
output:`No`

样例3. input:`8`
output:`Yes`

### 代码样例

```cpp
#include <iostream>
#include <cstring>
using namespace std;

bool func(char array[ ], int len) {
	//此处填补几行代码
    if(len==0 || len==1) return true;
    else 
        return (array[0]==array[len-1])&&func(array+1,len-2);
}


int main() {
    char ch[20];
    bool result;

    cin >> ch;

	//此处填补几行代码
    if(func(ch,strlen(ch)))cout<<"Yes";
    else cout<<"No";

    return 0;
}


```





## 7.1.4 函数补全

### 任务描述

把右侧代码补充完整，包括在main函数之前添加2行代码以及在最后添加一个函数的定义，使得该程序能在一行里输出三个数：输出的第一个数是x（即用户输入的第一个数）减去y（即用户输入的第二个数）的差的个位数，第二个数是x的3倍，第三个数是y的2倍。

### 说明

要求1：在“此处填补2行代码”的位置只能添加2行代码。
要求2：在“此处定义一个函数”的位置只能添加一个函数的定义。该函数体中只有2行代码，且不包含任何数组名、无输出操作。
要求3：注意输出的各个数之间都有个空格，与运行示例中格式一致。
要求4：不能在未标明的位置添加或修改代码。
注：上述“2行代码”的意思是只有2个分号，在参数表之外没有逗号。

### 样例输入输出

Input: `18 5`
Output: `3 54 10`

### 代码样例

```cpp
#include <iostream>
using namespace std;

//此处填补2行代码
char * myfun(int &a, int &b);
char s[3]="  ";
int myfun(int* a, int* b);
int main() {
    int x, y;
    cin >> x >> y;
    cout << myfun(x, y);
    cout << x << ' ' << y;
    return 0;
}
int myfun(int* a, int* b) {
    int c = *a - *b;
    *a *= 2;
    *b *= 3;
    return c;
}

//此处定义一个函数
char * myfun(int &a, int &b){
    s[0]='0'-myfun(&b, &a)%10;
    return s;
}
```



## 7.1.5 日期读取

### 任务描述

写一个函数getDate，从键盘读入一个形如dd-mmm-yy的日期。其中dd是一个1位或2位的表示日的整数，mmm是月份的3个字母的缩写，yy是两位数的年份。函数读入这个日期，并将它们以数字形式传给3个参数。

### 输入输出样例

样例1
input:`5-Mar-18`
output:`5 3 18`

样例2
input:`12-Mar-18`
output:`12 3 18`

### 代码样例

```cpp
#include <iostream>
#include <cstring>
using namespace std;
char *mth[12]={"Jan","Feb","Mar","Apr","May","Jun","Jul","Aug","Sep","Oct","Nov","Dec"};
void getDate(int &d, int &m, int &y){
    char s[10]={0};
    cin>>s;
    int i=0,j=0;
    d=s[0]-'0';
    if(s[1]!='-'){d=d*10+s[1]-'0';i=3;j=7;}
    else {i=2;j=6;}
    y=s[j]-'0';
    y=y*10+s[j+1]-'0';
    char sub[4]={0};
    for(int k=0;k<3;k++){
        sub[k]=s[i+k];
    }
    for(int k=0;k<12;k++){
        if(!strcmp(sub,mth[k])){m=k+1;break;}
    }

   
}

int main()
{
    int day, month, year;
    getDate(day, month, year);
    cout << day <<" "<< month<<" " << year << endl;
    return 0;
}
```



## 7.2.1 Julian历法

### 任务描述

Julian历法是用年以及这一年中的第几天来表示日期。设计一个函数，将Julian历法表示的日期转换成月和日，如Mar 8（注意闰年的问题）。函数返回一个字符串，即转换后的月和日。如果参数有错，如天数为第370天，返回NULL指针，此使屏幕无打印输出。

### 样例输入输出

样例1
input:
`2020` 
`1`
output:
`Jan 01`

样例2
input:
`1998`
`33`
output:
`Feb 2`

样例3
input:
`2020` 
`366`
output:
`Dec 31`

样例4
input:
`2100`
`388`
output:

### 代码样例

```cpp
#include <iostream>
#include <cstring>
using namespace std;

int mday[12]={31,28,31,30,31,30,31,31,30,31,30,31};
char* mname[12]={"Jan","Feb","Mar","Apr","May","Jun","Jul","Aug","Sep","Oct","Nov","Dec"};
char *julian(int year, int day){
    char* res=new char[10];
    bool run = (year%4==0)&&(year%100!=0)||(year%400==0);
    if(run)mday[1]=29;
    if(day<1||(run&&day>366)||(!run&&day>365)||(year<0))return NULL;
    int s=0;
    int i=0;
    for(;i<12;i++){
        s+=mday[i];
        if(s>=day)break;
    }
    strcpy(res,mname[i]);
    int ri=day+mday[i]-s;
    res[3]=' ';
    if(ri<10)res[4]='0';
    else{
        res[4]=ri/10+'0';
        ri=ri%10;
    }
    res[5]=ri+'0';
    res[6]=0;
    return res;
}
int main()
{
    int year,day;
    char* res;
    cin>>year>>day;
    res=julian(year,day);
    cout<<res<<endl;
    delete []res;
    return 0;
}
```



## 7.2.2 字符串处理排序

### 任务描述

输入若干个字符串(每个字符串的长度不超过30个字符，字符串总数不超过30)，和一个英文字符ch。 要求删除每个字符串中的字符ch(区分大小写)，得到新的字符串，然后将新的字符串按照字典逆序排序后输出。

### 输入输出样例

input:
`3`
`abcddc`
`sxwcdez`
`ncvccvd`
`c`
output:
`sxwdez`
`nvvd`
`abdd`样例

```cpp
#include <iostream>
#include <cstring>
using namespace std;

int main()
{    
    int n;
    char *string[30], ch;
    cin>>n;
    cin.get();
    for(int i=0; i<n; i++){
        string[i]=new char[30];
        cin.getline(string[i],30);
        
    }
    cin.get(ch);
    for(int i=0; i<n; i++){
        int j=0;
        while(string[i][j]){
            while(string[i][j]==ch){
                int k=j;
                while(string[i][k]){
                    string[i][k]=string[i][k+1];
                    k++;
                }
            }
            j++;
        }
    }
    bool flag = true;
    for(int i=0; i<n&&flag; i++){
        flag = false;
        for(int j=0; j<n-i-1; j++){
            if(strcmp(string[j],string[j+1])<0){
                flag=true;
                char *tmp=string[j];
                string[j]=string[j+1];
                string[j+1]=tmp;
            }
        }
    }
    for(int i=0; i<n; i++){
        cout<<string[i]<<endl;
    }

    return 0;
}
```





## 7.2.3 最大和第二大数

### 任务描述


本关任务：修改ppt中分治法求最大最小数的程序，使之能够求最大和第二大数，同时还要求尽量节约空间

### 编程要求

根据提示，在右侧编辑器补充代码，用户先输入元素个数n(n>2)，然后依次输入这n个整数，输出其中最大和第二大数

### 测试说明

平台会对你编写的代码进行测试：

测试输入：`5 4 -3 2 5 1`
预期输出：
`5 4`

### 代码样例

```cpp
#include <iostream>
using namespace std;

void max12(int *p, int n, int *m1, int *m2){
    int m1_1, m1_2, m2_1, m2_2;
    switch(n){
        case 1: *m1=p[0];*m2=0; return;
        case 2: if(p[0]<p[1]){
                    *m1=p[1];
                    *m2=p[0];
                }
                else{
                    *m1=p[0];
                    *m2=p[1];
                }
                return;
        default: max12(p,n/2,&m1_1,&m2_1);
                 max12(p+n/2,n-n/2,&m1_2,&m2_2);
                 if(m1_1>=m1_2){
                     *m1=m1_1;
                     if(m1_2>=m2_1)*m2=m1_2;
                     else *m2=m2_1;
                     }
                 else {
                     *m1=m1_2;
                     if(m2_2>=m1_1)*m2=m2_2;
                     else *m2=m1_1;
                     }
                 return;
    }
    
}
int main()
{    
    int n;
    int m1, m2;
    //int *p=new int[n];
    int p[1000];
    cin>>n;
    for(int i=0;i<n;i++){
        cin>>p[i];
    }
    max12(p,n,&m1,&m2);
    cout<<m1<<' '<<m2;
    //delete []p;
    return 0;
}
```



## 7.2.4 实现strrchr函数

### 任务描述


本关任务：实现cstring库的函数strrchr


### 编程要求

根据提示，在右侧编辑器补充代码，strrchr第一个参数为输入字符串，第二个参数为要查找的字符。返回一个指针，指向被查找的字符串在字符串中最后出现的位置。如果没有出现，返回空指针。字符串最大长度50。

### 测试说明

平台会对你编写的代码进行测试：

测试输入：
`asdfgfdsa`
`f`
预期输出：
`fdsa`

测试输入：
`asdgdsa`
`f`
预期输出：
`no`

### 代码样例

```cpp
#include <iostream>
using namespace std;

char* strrchr(char* str, char ch) 
{
    char* p=NULL;
    while(*str){
        if(*str==ch)p=str;
        str++;
    }
    return p;
}

int main()
{    
    char str[50], ch;
    cin.getline(str,50);
    cin>>ch;
    char *res=strrchr(str,ch);
    if(!res)cout<<"no";
    else cout<<res;

    return 0;
}
```



## 7.2.5 字符串奇数位置的序列

### 任务描述


本关任务：编写一个函数oddstr，将一个字符串奇数位置的字符构成一个字符串


### 编程要求

根据提示，在右侧编辑器补充代码，用户输入一个长度小于200的字符串，main函数通过调用oddstr得到该字符串奇数位置的字符构成的字符串，然后输出新的字符串


### 测试说明

平台会对你编写的代码进行测试：

测试输入：`123456`
预期输出：
`246`

### 代码样例

```cpp
#include <iostream>
using namespace std;

char *oddstr(char *str){
    char *odd=new char[100];
    int i=0,j=0;
    while(*str){
        if(i%2==1)odd[j++]=*str;
        str++;
        i++;
    }
    return odd;
}
int main() {
    char str[200];
    cin >> str;
    char *odd = oddstr(str);
    cout << odd << endl;
    delete []odd;
    return 0;
}
```



## 7.2.6 浮点数加法

### 任务描述

本关任务：实现两个正浮点数a, b的精确加法

### 编程要求

根据提示，在右侧编辑器补充代码，定义函数add_float(char* a, char* b, char* res)实现两个正浮点数a, b的精确加法。
注意：只需要实现函数add_float，函数中没有任何输入输出。
函数的输入参数char* a和char* b都是用字符串表示的正浮点数。保证a, b一定都包含一个字符是小数点'.'，保证其余字符全是0-9的数字。保证a, b不超过128个字符。
函数的输出参数char* res，保证浮点数a+b的结果不超过 128 个字符。
要求res字符串必须包含小数点'.'（即使结果是像下面 sample 1 这样并没有小数部分）。
要求res字符串没有任何多余的前缀字符'0'和后缀字符'0'（即使结果像下面 sample 2 这样没有整数部分）。
注意：虽然要求结果字符串res必须有小数点且没有任何前缀后缀0，但是并不保证字符串a, b满足这两点。


### 测试说明

平台会对你编写的代码进行测试：

测试输入：`0.1 0.9`
预期输出：
`1.`
注意：不是`1.0`

测试输入：`.01 .09`
预期输出：
`.1`
注意：不是`0.1`，也不是`0.10`

### 代码样例

```cpp
#include <iostream>
#include <cstring>
using namespace std;

void add_float(char* a, char* b, char* res) {
    int i=0, j=0;
    int ai[256]={0}, bi[256]={0}, resi[256]={0};
    while(a[i]){
        if(a[i]=='.')break;
        i++;
    }
    while(b[j]){
        if(b[j]=='.')break;
        j++;
    }
    int ade = strlen(a)-1-i;
    int bde = strlen(b)-1-j;
    int al = strlen(a);
    int bl = strlen(b);
    while(ade--){
        ai[127-ade]=a[--al]-'0';
    }
    while(bde--){
        bi[127-bde]=b[--bl]-'0';
    }
    int ii=0, jj=0;
    while(i--){
        ai[128+ii]=a[i]-'0';
        ii++;
    }
    while(j--){
        bi[128+jj]=b[j]-'0';
        jj++;
    }
    int jw=0, c=0;
    bool flag1 = true;
    for(int k=0; k<256; k++){
        resi[k]=(ai[k]+bi[k]+jw)%10;
        jw=(ai[k]+bi[k]+jw)/10;
        if(resi[k]==0&&flag1)c++;
        else flag1=false;
    }
    int rind = 0;
    bool flag = true;
    for(int k=255; k>=128; k--){
        if(resi[k]==0&&flag)continue;
        flag = false;
        res[rind++]=resi[k]+'0';
    }
    res[rind++]='.';
    for(int k=127; k>=c; k--){
        res[rind++]=resi[k]+'0';
    }
    res[rind]='\0';
}


int main()
{
    char num1[128], num2[128], res[128];
    cin >> num1;
    cin >> num2;
    add_float(num1, num2, res);
    cout << res << endl;
    return 0;
}
```



## 7.3.1 小写变大写

### 任务描述


本关任务：写出所给代码中的两个函数funA和funB的声明与定义，使得funA(p)=a能实现通过指针p访问用户输入的字符串a，funB能将该字符串中的小写字母全部变成大写，并返回这个大写的字符串。

### 编程要求

根据提示，在右侧编辑器补充代码，除了实现funA和funB外，不能修改包括main函数在内的其他代码，不能在全局定义新的变量、指针、数组和函数等，不能调用其他的库。
funA和funB内不能调用任何输入输出函数（包含但不限于cin,cout,scanf,prinf,getchar,putchar等等）。
不允许存在内存泄漏，由于EC不能检测内存泄漏(同学们可以自行了解内存泄漏检测工具valgrind)，助教将进行手动评测（以最后一次提交为准）。
每个测试用例有三行，每行对应一个字符串，长度不超过98，而且只含有小写和大写字母。
输出有三行，将输入转化为大写后，按顺序输出。


### 测试说明

平台会对你编写的代码进行测试：

测试输入：
`ieee`
`tryAtry`
`acisOK`
预期输出：
`IEEE`
`TRYATRY`
`ACISOK`

### 代码样例（By 林袁艺）

```cpp
#include <iostream>
#include <cstring>
using namespace std;

// 写出两个函数的声明
char* &funA(char**& p);
char* funB(char* b,char** p);

int main()
{
    char a[100], b[100];
    for(int i = 0; i < 3; ++i)
    {
        char **p;
        cin >> a;
        funA(p) = a;
        cout << funB(b, p) << endl;
    }
    return 0;
}

// 写出两个函数的定义
char* &funA(char**& p)
{
   p=new char*;
   return *p;

}
char* funB(char* b,char** p)
{
    //*的优先级比[]低
    int n=strlen(*p);
    for(int i=0;i<n;++i){
        if( ((*p)[i]>='a')&& ((*p)[i]<='z') ){b[i]=((*p)[i]+'A'-'a');}
        else{b[i]=(*p)[i];}
    }
    b[n]='\0';
    delete p;
    return b;
}
```



## 7.3.2 日期推算

### 任务描述


本关任务：设计一个程序用于向后推算指定日期经过n天后的具体日期。

### 编程要求

根据提示，在右侧编辑器补充代码，输入为长度为8的字符串str和一个正整数n，str前四位表示年份，后四位表示月和日。当推算出的年份大于4位数时，输出“out of limit!”，否则输出8位的具体日期。


### 测试说明

平台会对你编写的代码进行测试：

测试输入：
`00250709 60000`
预期输出：
`01891017`

### 代码样例（By 林袁艺）

```cpp
#include <iostream>
using namespace std;

int yearday(int year);
int convertchartoint(char* text,int length);
void converinttochar(int num,char* const text,int n);
void convertobegin(int &year,int &month,int &day,long int &n);

int main()
{
    char p[9];
    cin>>p;
    long int n;
    cin>>n;

    //将字符串中的年份移到int型变量year中
    int year=convertchartoint(p,4);
    //月份转移到int型变量month中
    int month=convertchartoint(p+4,2);
    //将几号转移到int型变量day中
    int day=convertchartoint(p+6,2);
    //往前数化归到起始日期为某年第一天的问题
    convertobegin(year,month,day,n);
    //求过了n天后是哪一年，结果为year,还剩下n天
    while(n>=0){
        n-=yearday(year);
        ++year;
    }
    --year;n+=yearday(year);
    if(year>=10000){cout<<"out of limit!";return 0;}

    //求过了n天后是哪一月,结果为month,还剩下n天
    int monthday[12]={31,( (yearday(year)==365)?28:29 ),31,30,31,30,31,31,30,31,30,31};
    while(n>=0){
        n-=monthday[month-1];//烦，month月有monthday[month-1]天！
        ++month;
    }
    --month;n+=monthday[month-1];
    //求是哪一天，结果为day
    day=n+1;

    //输出模块
    converinttochar(year,p+3,4);
    converinttochar(month,p+5,2);
    converinttochar(day,p+7,2);
    cout<<p<<endl;
    return 0;
}
//化归到起始日期为某年第一天的问题
void convertobegin(int &year,int &month,int &day,long int &n)
{
    n+=day-1;day=1;

    int monthday[12]={31,( (yearday(year)==365)?28:29 ),31,30,31,30,31,31,30,31,30,31};
    for(;month>1;--month){
        n+=(monthday[month-1-1]);
    }
}
//将整型放到text结尾且总长为n的字符串，前面补0，text下一位
void converinttochar(int num,char* const text,int n)
{
    text[1]='\0';
    for(int i=0;i<n;++i){
        text[0-i]=('0'+num%10);
        num/=10;
    }
}
//将一串字符转成整型
int convertchartoint(char* text,int length)
{
    int num=0;
    for(int i=0;i<length;++i){
        num=num*10+(text[i]-'0');
    }
    return num;
}
//计算这一年有几天
int yearday(int year)
{
    bool leapyear=false;
    if( ((year%4==0)&&(year%100!=0))||(year%400==0) ){leapyear=true;}
    return ((leapyear)?366:365);
}

```



## 7.3.3 字符串字符对调

### 任务描述


本关任务：设计一个程序，让用户输入两串字母，存入两个字符数组中，然后将它们中下标相同的非空字符对调，再输出这两个新的字符串。用户输入的两串字母都小于20个（大小写不限），不包含其它字符，以回车完成输入。


### 编程要求

根据提示，在右侧编辑器补充代码，用户输入两串字母，存入两个字符数组中，然后将它们中下标相同的非空字符对调，再输出这两个新的字符串。用户输入的两串字母都小于20个（大小写不限），不包含其它字符，以回车完成输入。限制要求如下：
a)	除了iostream之外不可包含其它库；
b)	只能定义两个长度为20的字符数组、一个字符变量、一个字符指针，不定义别的变量、数组或其它对象；
c)	对该字符变量只能进行赋值运算，不能进行算术或其它运算（包括复合赋值、自增自减等）。

  

### 测试说明

平台会对你编写的代码进行测试：

测试输入：
`ABCDEFGH`
`abcde`
预期输出：
`abcdeFGH`
`ABCDE`

### 代码样例

```cpp
#include <iostream>
using namespace std;

int main()
{
    char str1[20];
    char str2[20];
    char tmp, *p1, *p2;

    cin.getline(str1,20);
    cin.getline(str2,20);

    /*Start your code here*/
    for (p1=str1, p2=str2; *p1 && *p2; p1++, p2++)
        tmp = *p1, *p1 = *p2, *p2 = tmp;
    cout << str1 << endl;
    cout << str2 << endl;

    /*end your code*/
    return 0;
}
```



