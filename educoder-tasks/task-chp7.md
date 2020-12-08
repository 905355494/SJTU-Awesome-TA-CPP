# 实训作业参考答案 —— 第七章 指针（上、下）



## 7.1.1 任务名称

字符串对调

### 任务描述

设计一个程序，让用户输入两串字符，存入两个字符数组中，然后将它们中下标相同的非空字符对调，再输出这两个新的字符串。用户输入的两串字符数量都小于20个，以回车完成输入。

### 限制条件
1. 除了`<iostream>`之外不可包含其它库；
2. 只能定义两个长度为20的字符数组、一个字符变量、一个字符指针，不定义别的变量、数组或其它对象；
3. 对该字符变量只能进行赋值运算，不能进行算术或其它运算（包括复合赋值、自增自减等）。

### 输入输出示例
Input: 
`ABCDEFGH`
`abcde`
Output: 
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





## 7.1.2 任务名称

变换单词顺序

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
    /*Start your code here*/
    char *input = new char[110];
    char *output = new char[110];
    int *p2 = new int[20];
    int bias = 0;
    int i = 0;
    cin.getline(input,110);
    char *p1 = input;
    int count=0;
    while(*p1!=0){
        while(*p1==' '&&*p1!=0){ p1++; bias++;}
        if(*p1!=0){ count++; p2[i]=bias; i++;}
        while(*p1!=' '&&*p1!=0){ p1++; bias++;}
        p2[i]=bias; i++;
    }
    cout << count <<endl;
    char * order = new char[count+1];
    cin.getline(order,count+1);
    int m = 0;
    for(int j = 0;j<count;j=j+1){
        for(int k = p2[2*(order[j]-'0')];k<p2[2*(order[j]-'0')+1];k++){
            output[m] = input[k];
            m++;
        }
        output[m] = ' ';m++;
    }
    output[m-1]='\0';
    cout << output;


    /*end your code*/
    return 0;
}
```





## 7.1.3 任务名称

约瑟夫环问题

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
    /*Start your code here*/
    char *input = new char[110];
    char *output = new char[110];
    int *p2 = new int[20];
    int bias = 0;
    int i = 0;
    cin.getline(input,110);
    char *p1 = input;
    int count=0;
    while(*p1!=0){
        while(*p1==' '&&*p1!=0){ p1++; bias++;}
        if(*p1!=0){ count++; p2[i]=bias; i++;}
        while(*p1!=' '&&*p1!=0){ p1++; bias++;}
        p2[i]=bias; i++;
    }
    cout << count <<endl;
    char * order = new char[count+1];
    cin.getline(order,count+1);
    int m = 0;
    for(int j = 0;j<count;j=j+1){
        for(int k = p2[2*(order[j]-'0')];k<p2[2*(order[j]-'0')+1];k++){
            output[m] = input[k];
            m++;
        }
        output[m] = ' ';m++;
    }
    output[m-1]='\0';
    cout << output;


    /*end your code*/
    return 0;
}

```





## 7.1.4 任务名称

加密字符

### 任务描述

编写程序，将输入的一个字符串进行加密和解密。加密时，每个字符依次反复加上“8734962”中的数字，如果范围超过ASCII码的032（空格）- 122（\`z\`），则进行模运算。解密与加密的顺序相反。请编写加密和解密的过程，并打印出结果。注：要加密的字符串长度不会超过30。

### 说明
1. 字符的范围。无论时输入的字符还是加密后的字符，字符的ASCII值都需要控制在032（空格）- 122（'z'）之间，即[32,122]
2. 加密。把待加密字符串7个字符分为一组，每组对应位依次加上“8734962”中的数字。如果执行加法后得到的数值N超过[32,122]，则需要调整。加密公式为32+(N-32)%(122-32+1)，当N>122时在本题目中加密公式可简化为N%91或N-91。
3. 解密。解密的过程与加密的过程顺序正好相反。如果执行减法后得到的数值不在[32,122]，则需要调整。解密公式为32+[N-32+(122-32+1)]%(122-32+1)；当N＜32时在本题目中可简化为N+91.


### 输入输出示例

input: 
`wherewithal`

output:
`$ohvn"k!odp"`
`wherewithal`


| 待加密字符 | 加法运算  | 加密后字符的ASCII码 | 加密后字符 | 减法运算  | 解密后字符的ASCII码 | 解密后字符 |
| ---------- | --------- | ------------------- | ---------- | --------- | ------------------- | ---------- |
| w          | 119+8=127 | 127%91=36           | $          | 36-8=28   | 28+91=119           | w          |
| h          | 104+7=111 | 111                 | o          | 111-7=104 | 104                 | h          |
| e          | 101+3=104 | 104                 | h          | 104-3=101 | 101                 | e          |
| r          | 114+4=118 | 118                 | v          | 118-4=114 | 114                 | r          |
| e          | 101+9=110 | 110                 | n          | 110-9=101 | 101                 | e          |
| w          | 119+6=125 | 125%91=34           | "          | 34-6=28   | 28+91=119           | w          |
| i          | 105+2=107 | 107                 | k          | 107-2=105 | 105                 | i          |
| t          | 116+8=124 | 124%91=33           | !          | 33-8=25   | 25+91=116           | t          |
| h          | 104+7=111 | 111                 | o          | 111-7=104 | 104                 | h          |
| a          | 97+3=100  | 100                 | d          | 100-3=97  | 97                  | a          |
| l          | 108+4=112 | 112                 | p          | 112-4=108 | 108                 | l          |

### 代码样例

```cpp
#include <iostream>
using namespace std;

void encrypt(char * s)
{
    // write your code here
    int t[7] = {8,7,3,4,9,6,2};
    for (int i=0;s[i];i++) {
        s[i] += t[i%7];
        if (s[i] > 122) s[i] -= 91;
    }
}
void decrypt(char * s)
{
    // write your code here
    int t[7] = {8,7,3,4,9,6,2};
    for (int i=0;s[i];i++) {
        s[i] -= t[i%7];
        if (s[i] < 32) s[i] += 91;
    }
}
// do not change main function
int main(void)
{
    char s[35];
    cin.getline(s, 31);
    encrypt(s);
    cout << s << endl;
    decrypt(s);
    cout << s << endl;

    return 0;
}
```



## 7.1.5 任务名称

敏感词过滤

### 任务描述

实现一个敏感词汇的程序。规则如下：
1. 能接受的字符：①字母；②数字；③三个标点符号,."；④空格；⑤三个无用的符号@#$。
2. 对于敏感信息的词汇不区分大小写。
3. 要注意滤去可能在敏感词汇的中间出现的一些空格（比如要滤去lv，输入l  v时要辨认出来并滤去）。
3. 若有用信息（字母、数字）中夹杂着无用的符号，也要辨认出并滤去。假如敏感词汇是mz，那么m#z也要滤去，但是输入ml,z不用滤去。

要求说明：要过滤的词汇只有L4和Fd和D2这三个词，并且输入的字符串长度不能大于20个字符。

### 输入输出样例
样例1
input:`L^67d*`
output:`输入不符合要求`

样例2
input:`@#$,."`
output:`@#$,."`

样例3
input:`# f@#$$#d #`
output:`#  #`

样例4
input:`f$#d26`
output:`26`

样例5
input:`Ld2648`
output:`8`

样例6
input:`12345678901234567890123`
output:`输入不符合要求`

### 代码样例

```cpp
#include <iostream>
#include <cstring>
using namespace std;
int main(){
	char *p = new char[200];
	int *d = new int[200];
	cin.getline(p, 200);
    int n = strlen(p);
    for (int i=0;i<n;i++) d[i]=0;
    int epoch = 0;
    while (true){
    	//cout<<"this is epoch: "<<epoch<<"-- ";
    	epoch+=1;
    	int flag = 0;
	    for (int i=0;i<n;i++){
	    	if (d[i]==0){
		    	if (p[i] == 'L' || p[i] == 'l'){
		    		int clear = 1;
		    		int has = 0;
		    		for (int j=i+1;j<n;j++){
		    			if (d[j]==0){
			    			if (p[j]=='@'||p[j]=='$'||p[j]=='#'){
			    				clear = 1;
			    				//cout<<"this"<<epoch<<" "<<clear<<endl;
							}
							else if (p[j] == '4' && clear == 1){
								for (int k=i;k<=j;k++){
									d[k] = 1;
								}
								has = 1;
								break;
							}
							else {
								clear = 0;
								break;
							}
						}
					}
					if (has == 1) flag = 1;
		        }
		        
		        if (p[i] == 'F' || p[i] == 'f'){
		    		int clear = 1;
		    		int has = 0;
		    		for (int j=i+1;j<n;j++){
		    			if (d[j]==0){
			    			if (p[j]=='@'||p[j]=='$'||p[j]=='#'){
			    				clear = 1;
			    				//cout<<"this"<<epoch<<" "<<clear<<endl;
			    				//cout<<p[j]<<" ";
							}
							else if ((p[j] == 'd' || p[j] == 'D') && clear == 1){
								for (int k=i;k<=j;k++){
									d[k] = 1;
								}
								has = 1;
								break;
							}
							else {
								clear = 0;
								break;
							}
						}
					}
					if (has == 1) flag = 1;
		        }
		    }
		}
		if (flag == 0) break;
	}
	for (int i=0;i<n;i++){
		if (d[i] == 0){
			cout<<p[i];
		}
	}
}
```





## 7.1.6 任务名称

单位换算（提高题）

### 任务描述

编写一个程序，实现长度单位由公制到英制的换算。程序应该允许用户指定单位的名字（它们都是字符串），并且可以询问用户是否继续运行。对于公制系统，也就是millimeter（毫米）、centimeter（厘米）、decimeter（分米）、meter（米）等，对于英制系统，也就是inch（英寸）、feet（英尺）、yards（码）等，如下表所示。


| 长度单位公制到英制转换                                       |
| ------------------------------------------------------------ |
| 1 millimeter（毫米）= 0.0394 inch（英寸）                    |
| 1 centimeter（厘米）= 10 millimeter（毫米）= 0.394 inch（英寸） |
| 1 decimeter（分米）= 10（厘米）= 3.94 inches（英寸）         |
| 1 meter（米）= 10（分米）=1.0936 yards（码）= 3.28 feet（英尺） |

### 程序运行示例
黑色的部分是程序的输出，红色部分是系统给程序的输入。
`Please input:`
<font color=red>`How many inches are in 2 meters ?`</font>
`78.8`
`Go on?(y/n):`<font color=red>`y`</font>
`Please input:`
<font color=red>`How many inches are in 3 decimeters ?`</font>
`11.82`
`Go on?(y/n):`<font color=red>`n`</font>

### 代码样例

```cpp

```





## 7.2.1 任务名称

再次判断回文数

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

bool func(char array[ ], int len);

int main() {
    char ch[20];
    bool result;

    cin >> ch;

	//此处填补几行代码
    if (func(ch,strlen(ch))) cout << "Yes";
    else cout << "No";

    return 0;
}

bool func(char array[ ], int len) {
	//此处填补几行代码
    if(len==1||len==0) return true;
    if(func(array+1,len-2)&&array[0]==array[len-1]) return true;
    else return false;
}
```





## 7.2.2 任务名称

函数补全

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

int myfun(int* a, int* b);
// do not change main function
int main() {
    int x, y;
    cin >> x >> y;
    cout << myfun(&x, &y) << ' ';
    cout << x << ' ' << y;
    return 0;
}

int myfun(int* a, int* b) {
    // write your code here
    int x=(*a-*b)%10;
    *a*=3;
    *b*=2;
    return x;
}
```





## 7.2.3 任务名称

日期读取

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
using namespace std;

char* getDate(int& day, int& month, int& year)
{
	// write your code here
    char* a = new char[10];
    for (int i=0;i<10;i++){
    	cin>>a[i];
	}
	day = (a[0]-'0')*10+(a[1]-'0');
	month = (a[3]-'0')*10+(a[4]-'0');
	year = (a[6]-'0')*1000 + (a[7]-'0')*100 + (a[8]-'0')*10 + (a[9]-'0');
	//return a;
}
// dont change main function
int main()
{
    int day, month, year;
    getDate(day,month,year);
    cout<<" "<<day<<" "<<month<<" "<<year<<endl;
    return 0;
}

```





## 7.2.4 任务名称

删除相同字符（递归版实现）

### 任务描述

设计一个函数void deletechar(char *str1, const char *str2)，在str1中删除str2中出现的字符。用递归实现

### 输入输出样例
样例1
input:
`Iwannarock`
`rock`
output:
`Iwanna`

样例2
input:
`small dog little eyes`
`dog`
output:
`small  little eyes`

### 代码样例

```cpp

```



## 7.2.5 任务名称

删除相同字符（非递归版本）

### 任务描述


设计一个函数void deletechar(char *str1, const char *str2)，在str1中删除str2中出现的字符。用非递归方法实现。

### 输入输出样例
input:
`Iwannarock`
`rock`
output:
`Iwanna`

### 代码样例

```cpp
#include <iostream>
#include <cstring>
using namespace std;

void deletechar(char* str1, const char* str2) {
	// write your code here
    int l1 = strlen(str1);
	int l2 = strlen(str2);
	char *str = new char[85];
	int p = 0;
	//cout<<l1<<" "<<l2<<endl;
	for (int i=0;i<l1;i++){
		char c = str1[i];
		int flag = 1;
		for (int j=0;j<l2;j++){
			if (str2[j] == c) {
				//cout<<c<<" ";
				flag = 0;
				break;
			}
		}
		if (flag == 1) {
			str[p] = c;
			p+=1;
		}
	}
	int n = strlen(str);
	strcpy(str1, str);
}

int main() {
	char str1[85], str2[85];
	cin.getline(str1, 80);
    cin.getline(str2, 80);
    
	deletechar(str1, str2);

    cout<<str1<<endl;
	return 0;
}
```





## 7.2.6 任务名称

Julian历法

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
 
char* julian(int year, int days);

int main() {
    int year, day;
    char * res;
    cin >> year >> day;
    res = julian(year, day);
    if (res) cout << res << endl;
    delete [] res;
    return 0;
}

char* julian(int year, int days){
	char monthen[12][5] = {
	"Jan","Feb","Mar","Apr","May",
	"Jun","Jul","Aug","Sept","Oct",
	"Nov","Dec"
	};
	int *a = new int[4];
	if (year < 0) return NULL;
	if (days < 1) return NULL;
	bool judge;
 
	if (year % 100 == 0){
		if (year % 400 == 0) judge = true;
		else judge = false;
	}
	else{
		if (year % 4 == 0) judge = true;
		else judge = false;
	}
	if (judge == true){
		if (days > 366) return NULL;
		int month = 0;
		for (int i : {31, 29, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31}){
			month = month + 1;
			if (days < i){
				int j;
				for (j = 1; ; j--){
					a[j] = (month % 10);
					month = month / 10;
					if (month == 0) break;
				}
				for (j = 3; ; j--)
				{
					a[j] = (days % 10);
					days = days / 10;
					if (days == 0) break;
				}
				break;
			}
			else days = days - i;
		}
	}
	else{
		if (days > 365) return NULL;
		int month = 0;
		for (int i : {31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31}){
			month = month + 1;
			if (days < i){
				int j;
				for (j = 1; ; j--){
					a[j] = (month % 10);
					month = month / 10;
					if (month == 0) break;
				}
				for (j = 3; ; j--)
				{
					a[j] = (days % 10);
					days = days / 10;
					if (days == 0) break;
				}
				break;
			}
			else days = days - i;
		}
	}
	char *res;
	char *p = new char[3];
	p[0] = ' ';
	p[1] = a[2] + '0';
	p[2] = a[3] + '0';
	strcat(res, monthen[a[0]*10+a[1]-1]);
	strcat(res, p);
	return res;
}

```





## 7.2.7 任务名称

字符串处理排序

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

```



