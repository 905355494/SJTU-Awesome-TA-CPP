# 实训作业参考答案 —— 第四章 循环程序设计
## 5.1 任务名称

数组排序

### 任务描述


本关任务：输入一个正整数 n（n<100），然后再输入 n 个整数，将它们从大到小排序后输出。


### 编程要求

根据提示，在右侧编辑器补充代码，用户输入一个正整数n，然后再输入n个整数，将它们从大到小排序后输出。

### 测试说明

平台会对你编写的代码进行测试：

测试输入：5 88 55 77 44 99
预期输出：
99 88 77 55 44


### 代码样例

```c
#include <iostream>
using namespace std;
//冒泡排序
int main()
{
    int a[100] ,n,tmp;
    bool flag=false;
    cin>>n;

    for (int i=0;i<n;++i){
        cin>>a[i];
    }

    for(int i=0;i<n-1;++i){
        flag=false;
        for(int j=n-1;j>i;--j){
            if (a[j]>a[j-1]) {tmp=a[j];a[j]=a[j-1];a[j-1]=tmp;flag=true;}
        }
        if (!flag) {break;}
    }

    for (int i=0;i<n;++i){
        cout<<a[i]<<" ";
    }
    return 0;
}
```
## 5.2 任务名称

开灯问题

### 任务描述


本关任务：有n盏灯，编号为1~n。第1个人把所有灯打开，第2个人按下所有编号为2的倍数的开关（这些灯将被关掉），第3个人按下所有编号为3的倍数的开关（其中关掉的灯将被打开，开着的灯将被关闭），依次类推。一共有k个人，问最后有哪些灯开着？


### 编程要求

根据提示，在右侧编辑器补充代码，输入正整数n和k（k≤n≤1000），从小到大输出开着的灯的编号。

### 测试说明

```c
#include <iostream>
using namespace std;

int main()
{
    int n,k;
    int a[1001]={0};
    cin>>n>>k;
    for (int i=1;i<=k;++i){
        for (int j=1;j<=n;++j){
            if (j%i==0) {a[j]++;}
        }
    }

    for (int i=1;i<=n;++i){
        if (a[i]%2==1) {cout<<i<<" ";}//计算开关灯的次数，奇数次=开着
    }
    return 0;
}
```

另一种用布尔值标识开关的思路：

```C++
#include <iostream>
using namespace std;

int main()
{
    int n,k;
    cin>>n>>k;
    //1=开，0=关;数组初始化为n+1，把第一个元素忽略掉
    bool a[n+1]={0};
    //外层：对人进行
    for (int i=1;i<=k;++i){
        //内层：对灯进行
        for (int j=1;j<=n;++j){
            if (j%i==0) a[j]=(!a[j]);
        }
    }
    for (int i=1;i<=n;++i){
        if (a[i]) cout<<i<<" ";
    }
    return 0;
}

```
## 5.3 任务名称

黑色星期五

### 任务描述


本关任务：黑色星期五是指某天既是13号又是星期五。13号在星期五比在其他日子少吗？为了回答这个问题，编写一个程序，计算每个月的13号落在周一到周日的次数。



### 编程要求

根据提示，在右侧编辑器补充代码，用户输入正整数n，n为正整数且不大于400。要求计算从1900年1月1日至1900+n-1年12月31日中13 号落在周一到周日的次数（已知1900年1月1日是星期一）。

### 测试说明

平台会对你编写的代码进行测试：

测试输入：20
预期输出：
34 33 35 35 34 36 33
输出说明：以上7个数依次为星期一至星期日的天数

### 代码样例

```c
#include <iostream>
using namespace std;

int main()
{
    int n,sum=0,num[7]={0},l=0;
    cin >> n;
    int day[13]={0,31,28,31,30,31,30,31,31,30,31,30,31};
    for (int k=1;k<=n;++k)
    {
        for (int j=0;j<12;++j)
        {
            if ((1900+(k-1))%4==0&&(1900+(k-1))%100!=0||(1900+(k-1))%400==0)
                day[2]=29;
            else
                day[2]=28;
            sum+=day[j];
            sum+=13;
                switch (sum%7)
                {
                    case 0:++num[6];break;
                    case 1:++num[0];break;
                    case 2:++num[1];break;
                    case 3:++num[2];break;
                    case 4:++num[3];break;
                    case 5:++num[4];break;
                    case 6:++num[5];break;
                }
            sum-=13;
        }
        sum+=31;
    }
    for (int s=0;s<7;++s)
    {
        cout << num[s] << " ";
    }
    return 0;
}

```

## 5.4 任务名称


```c    //by李宇轩
#include <iostream>
using namespace std;

int main()
{
    int a[1000],b[1000],num=0,i=0;
    while (cin >> a[i])
    {
        for (int j=0;j<i;++j)
        {
            if (a[j]==a[i])
            {
                ++num;
            }
        }
        if (num==0)
        {
            b[i]=a[i];
            ++i;
            num=0;
        }
        else
            num=0;
    }
    for (int k=0;k<i;++k)
    {
        cout << b[k] << " ";
    }
    return 0;
}

```
## 5.5

```c
#include <iostream>
using namespace std;

int main()
{
    int a[1000],i=0,num=0;
    while (cin >> a[i])
    {
        for (int j=0;j<i;++j)
        {
            if (a[j]==a[i])
            {
                ++num;
            }
        }
        if (num==0)
        {
            ++i;
            num=0;
        }
        else
            num=0;
    }
    cout << i << " ";
    for (int k=0;k<i;++k)
    {
        cout << a[k] << " ";
    }
    return 0;
}

```
## 5.6 任务名称

回文数

### 任务描述


本关任务：回文数是指从左向右念和从右向左念都一样的数。如 12321 就是一个典型的回文数。给定一个进制 B（2≤B≤20，由十进制表示），求出所有的大于等于 1 小于等于 200（十进制下）且它的平方用 B 进制表示是回文数的数。用“A”，“B”，“C”…表示 10，11，12 等等。


### 编程要求

根据提示，在右侧编辑器补充代码，输入整数 B（B 由十进制表示），输出分成多行，每行输出两个 B 进制的数字，第二个数是第一个数的平方，且第二个数是回文数。

### 测试说明

平台会对你编写的代码进行测试：

测试输入：8
预期输出：
1 1
2 4
3 11
6 44
11 121
13 171
33 1331
101 10201
111 12321
117 14141
121 14641
123 15351
303 112211

### 代码样例

```c
#include <iostream>
using namespace std;

int main()
{
    int base;
    bool flag;
    cin >> base;
    for (int i=1;i<201;i++)
    {
        int a[100]={0},b[100]={0};
        flag=true;
        for (int i0=i*i;i0;i0/=base)
        {
            a[++a[0]]=i0%base;
        }
        for (int i=1,j=a[0];i<j;i++,j--)
        {
            if (a[i]!=a[j])
            {
                flag=false;
            }
        }
            if (flag)
            {
                for (int i0=i;i0;i0/=base)
                {
                    b[++b[0]]=i0%base;
                }
                for (int j=b[0];j>=1;j--)
                {
                    char x=(b[j]<10?b[j]+'0':b[j]-10+'A');
                    cout << x;
                }
                cout << " ";
                for (int j=a[0];j>=1;j--)
                {
                    char x=(a[j]<10?a[j]+'0':a[j]-10+'A');
                    cout << x;
                }
                cout << endl;
            }
    }
    return 0;
}

```
## 5.7 任务名称

寻找鞍点-二维数组

### 任务描述


本关任务：在矩阵中，一个元素在所在行中是最大值，在所在列中是最小值，则被称为鞍点（Saddle point）。求所给矩阵的鞍点


### 编程要求

根据提示，在右侧编辑器补充代码，用户输入两个正整数 m 和 n（m，n≤10），然后输入该 m 行 n 列矩阵 mat 中的元素，如果找到 mat 的鞍点，就输出它的下标；如果找到多个鞍点，则分行输出它们的下标（行下标小的鞍点优先输出）；否则，输出“Not Found”。

### 测试说明

平台会对你编写的代码进行测试：

测试输入：3 3 5 1 2 1 1 1 2 1 5
预期输出：
mat[1][0]=1
mat[1][1]=1
mat[1][2]=1

```c    //by 李瑞
#include <iostream>
using namespace std;

int main()
{
int m, n;
	cin >> m >> n;
	int mat[9][9];
	//输入一个二维矩阵
	for (int i = 0; i < m; ++i)
	{
		for (int j = 0; j < n; ++j)
		{
			cin >> mat[i][j];
		}
	}
	//判断鞍点(要先选出行最大，然后判断是否为列最小）
	int max[9] = { 0 };
	int min[9] = { 9 ,9,9,9,9,9,9,9,9 };
	int temp1[9] = { 0 };
	int temp2[9] = { 0 };
	int flag = 0;
	int i = 0;
	int j = 0;
	for ( i = 0; i < m; ++i)
	{
		for ( j = 0; j < n; ++j)
		{
			if (mat[i][j] >= max[i])
			{
				max[i] = mat[i][j];//找到每行最大的数
				temp1[i] = j;
			}
		}
	}
	
	for (j = 0; j < n; ++j)
	{
		for (i = 0; i < m; ++i)
		{
			if (mat[i][j] <= min[j])
			{
				min[j] = mat[i][j];
				temp2[j] = i;//找到每列最小的数
			}
		}
	}
	
	int a, b;
	a = b = 0;
	for (a = 0; a < m; ++a)
	{
		for (b = 0; b < n; ++b)
		{
			if (mat[a][b] == max[a] && mat[a][b] == min[b])
			{
				flag = 1;
				cout << "mat[" << a << "][" << b<< "]=" << mat[a][temp1[a]] << endl;
			}
		}
	}
	if (flag == 0)
		cout << "Not Found";
    return 0;
}
```
## 5.8 

```c
#include <iostream>
#include <cmath>
using namespace std;

int main()
{
char ch[80] ;
	int digit[80] = { 0 };
	int num = 0;
	int n = 0;
	cin.getline(ch, 80);
	int i;
	for (i = 0; ch[i] != '\0'; ++i)
	{
		if (ch[i] >= '0'&&ch[i] <= '9')
		{
			++num;
			digit[n] = ch[i] - 48;
			++n;
		}
	}
	int a = 0;
	for (int i = 0; i < num; ++i)
	{
		a += digit[i] * pow(10, num - i - 1);
	}
	int b;
	b = a * 2;
	cout << b;
    return 0;
}
```
## 5.9 任务名称

统计元音字母个数

### 任务描述


本关任务：输入一个字符串（少于80个字符），统计并输出其中元音字母（AEIOUaeiou）的个数（不区分大小写）。


### 编程要求

根据提示，在右侧编辑器补充代码，用户输入一个字符串（少于80个字符），统计并输出其中元音字母（AEIOUaeiou）的个数

### 测试说明

平台会对你编写的代码进行测试：

测试输入：I have an apple
预期输出：
6

```c
#include <iostream>
using namespace std;

int main()
{
char ch[80] ;
	int digit[80] = { 0 };
	int num = 0;
	int n = 0;
	cin.getline(ch, 80);
	int i, j;
	for (i = 0; ch[i]!='\0'; ++i)
	{
		
		if (ch[i]=='a'||ch[i]=='e'||ch[i]=='i'||ch[i]=='o'||ch[i]=='u'||ch[i]=='A'||ch[i]=='E'||ch[i]=='I'||ch[i]=='O'||ch[i]=='U' )
		{
			++num;
			digit[n] = ch[i] - 48;
			++n;
		}
	}
	cout << num;
    return 0;
}
```
## 5.10 任务名称

查找字符

### 任务描述


本关任务：编写一个程序，首先输入一个字符串（少于80个字符），接着再输入一个字符，查找该字符在字符串中是否存在。如果找到，则输出该字符串在字符串中所对应的最大下标（下标从0开始）；否则输出“Not Found”


### 编程要求

根据提示，在右侧编辑器补充代码，用户输入一个字符串（少于80个字符），接着再输入一个字符，输出该字符串在字符串中所对应的最大下标（下标从0开始），或者否则输出“Not Found”

### 测试说明

平台会对你编写的代码进行测试：

测试输入：
Hello, world! 
l
预期输出：
10

```c
#include <iostream>
using namespace std;

int main()
{
	char ch[80]={0} ;
	
	int num = 0;
	cin.getline(ch, 80);
	
	int i, j;
	char a;
	cin.get(a);
	for (i = 79; i>=0; --i)
	{
		
		if (ch[i]==a)
		{
			++num;
			break;
		}
	}
	if (num != 0)
		cout << i;
	if (num == 0)
		cout << "Not Found";
    return 0;
}
```
## 5.11 

```c    //by 罗锦润
#include<bits/stdc++.h>
using namespace std;
string s,t;
int n,m,f;
int main() {
	getline(cin,s);getline(cin,t);
	n=s.size();m=t.size();
	for(int i=0;i<=n-m;++i) {
		int fl=1;
		for(int j=i;j<i+m;++j)
			if(s[j]!=t[j-i])
				{fl=0;break;}
		if(fl) {f=1;cout<<i;break;}
	}
	if(!f) cout<<"-1";
	return 0;
}

```
## 5.12

```c
#include<bits/stdc++.h>
using namespace std;
string s;
int n,a,b,c;char op;
int main() {
	cin>>s;int i,j;
	n=s.size();
	for(i=0;i<n && isdigit(s[i]);++i) a=a*10+s[i]-'0';
	op=s[i++];
	for(;i<n;++i) b=b*10+s[i]-'0';
	if(op=='+') c=a+b;
	if(op=='-') c=a-b;
	if(op=='*') c=a*b;
	if(op=='/') c=a/b;
	printf("%d%c%d=%d",a,op,b,c);
	return 0;
}
```
## 5.13 任务名称

第一次和最后一次

###任务描述


本关任务：对于一个给定的有序数组，求出目标值x在该数组中第一次和最后一次出现的位置


###编程要求

根据提示，在右侧编辑器补充代码，用户先输入n，然后输入一个规模为n的有序数组，再输入目标值下，求出目标值x在该数组中第一次和最后一次出现的位置，如果x未出现在数组中，输出两个-1。请尽量提高计算效率。

###测试说明

平台会对你编写的代码进行测试：

测试输入：6 5 7 7 8 8 10 8
预期输出：
3 4
输出说明：数组为{5,7,7,8,8,10}

```c
#include <iostream>
using namespace std;

int main()
{
int a[200];
	int n, x, j;
    int num = 0;
	cin >> n;
	for (int i = 0; i < n; ++i){cin >> a[i];}
	cin >> x;

	for (j = 0; j < n; ++j)
	{
		if (a[j] == x)
		{
			cout << j<<" ";  ++num; break;
		}
	}
	for (j = n - 1; j >= 0; --j)
	{
		if (a[j] == x)
		{
			cout << j; ++num; break;
		}
	}
	if (num == 0)
		cout << "-1 -1";
    return 0;
}

```
## 5.14

```c
#include <iostream>
using namespace std;

int main()
{
    int n;
    cin>>n;
    int a[n];
    cin>>a[0];

    for(int i=1,t;i<n;++i)
    {
        cin>>a[i];
        t=a[i];
        int tmp=0,p=i-1;

        while(a[p+1]<a[p]&&p>=0){
                tmp=a[p];
                a[p]=t;
                a[p+1]=tmp;
                p-=1;
        }
    }
    for(int k=0;k<n;++k){cout<<a[k]<<" ";}
    return 0;
}
```
## 5.15 任务名称

字符重排序

###任务描述

本关任务：输入一个字符串（少于80个字符），去掉重复的字符后，按照字符的ASCII码值从大到小输出。

###编程要求

根据提示，在右侧编辑器补充代码，用户输入一个字符串（少于80个字符），去掉重复的字符后，按照字符的ASCII码值从大到小输出。

###测试说明

平台会对你编写的代码进行测试：

测试输入：ya7bb2tizx4m55n9q2
预期输出：
zyxtqnmiba97542

```c    //by 林洲谊
#include <iostream>
using namespace std;
char c;
int a[256];
int main()
{
    c=getchar();
    while(c!=EOF)
    {
        ++a[c];
        c=getchar();
    }
    for(int i=255;i>=1;--i){
    if(a[i])putchar(i);
    }

    return 0;
}
```
另一种C++风格的
```C++
#include <iostream>
using namespace std;

int main()
{
    int a[256];//a[i]存储ASCII码为i的字符出现的次数
    char c;
    //初始化
    for(int i=0;i<256;++i){
        a[i]=0;
    }
    //写入循环
    while(cin.get(c)){
        ++a[c];//把c隐式转换成int类型
    }
    //输出循环
    for(int i=255;i>=0;--i){
        if(a[i]!=0){
            c=i;//把a[i]隐式转换成char类型
            cout<<c;
        }
    }
    return 0;
}
```
## 5.16 任务名称

字符数统计

### 任务描述


本关任务：编写一个程序，从键盘上输入一篇英文文章，统计出其中的英文字母（不区分大小写）、数字和其他非空白字符的个数。


### 编程要求

根据提示，在右侧编辑器补充代码，用户首先输入英文文章的行数n（1≤n≤10），接着依次输入n行内容（每行少于80个字符）。要求统计出其中的英文字母（不区分大小写）、数字和其它非空白字符的个数。


```c
#include<bits/stdc++.h>
using namespace std;
int n,m,lt,dg,oth;
string s;
int main() {
	cin>>n;getchar();
	for(int i=0;i<n;++i) {
		getline(cin,s);m=s.size();
		for(int j=0;j<m;++j) {
			if(islower(s[j]) || isupper(s[j])) ++lt;
			else if(isdigit(s[j])) ++dg;
			else if(!isspace(s[j])) ++oth;
		}
	}
	printf("英文字母：%d\n",lt);
	printf("数字：%d\n",dg);
	printf("其他字符：%d\n",oth);
    return 0;
}

```
## 5.17 任务描述

插入位置

### 任务描述

本关任务：已知一个规模为n的有序整数数组，再输入整数x，判断x是否在数组中，如果是，则输出相应下标，如果否，则x插入数组哪个位置能够使数组仍然有序。

### 编程要求

根据提示，在右侧编辑器补充代码，输入正整数n(n<1000)，再输入n个有序整数以构成数组，再输入整数x，判断x是否在数组中，如果是，则输出相应下标，如果否，则求出x插入数组哪个位置能够使数组仍然有序。尽量提高算法效率。

### 测试说明

平台会对你编写的代码进行测试：

测试输入：4 1 3 5 6 5
预期输出：
2
输出说明：数组为{1，3，5，6}，5的下标为2

测试输入：4 1 3 5 6 2
预期输出：
1
输出说明：数组为{1，3，5，6}，2如果放在第1位则仍然有序

```c
#include<bits/stdc++.h>
using namespace std;
int n,x,a[1007];
int main() {
	cin>>n;
	for(int i=0;i<n;++i) cin>>a[i];
	cin>>x;
	int pos=find(a,a+n,x)-a;
	if(pos<n) cout<<pos;
	else cout<<lower_bound(a,a+n,x)-a;
    return 0;
}

```
另一种不使用STL算法的
```C++
#include <iostream>
using namespace std;

int main()
{
    int n;
    cin>>n;
    int a[n];
    //写入
    for (int i=0;i<n;++i){
        cin>>a[i];
    }
    int x;
    cin>>x;
    //判断
    for (int i=0;i<n;++i){
        if (a[i]==x){
            cout<<i;
            return 0;
        }
        if (a[i]>x){
            cout<<i;
            return 0;
        }
    }
    cout<<n;

    return 0;
}
```
## 5.18 任务名称

1的个数

### 任务描述


本关任务：A是一个n行n列的0-1矩阵(n<20)，每行的1都在0的前面，如何确定哪一行的1最多。


### 编程要求

根据提示，在右侧编辑器补充代码，先输入n，然后输入整个矩阵，输出1的个数最多的行的序号。如果有多行1的个数都是最多，输出序号最小的。思考一下如何提高程序执行效率。

###测试说明

平台会对你编写的代码进行测试：

测试输入：
3
1 1 0
1 1 1
1 0 0
预期输出：
1
输出说明：由于第一行有3个1，在所有的行中最多


```c
#include<bits/stdc++.h>
using namespace std;
int n,mx=-1,id;
int main() {
	cin>>n;
	//因为矩阵完全由0和1组成，可以用每行的和来标识1的个数
	for(int i=0,cnt;i<n;++i) {
		for(int a,j=cnt=0;j<n;++j) cin>>a,cnt+=a;
		if(cnt>mx) mx=cnt,id=i;
	}
	cout<<id;
    return 0;
}
```
## 5.19 任务名称

奇数位置的字符

### 任务描述


本关任务：编写一个程序，能够将所给字符串奇数位置的字符重新构成一个新的字符串并输出。


###编程要求

根据提示，在右侧编辑器补充代码，首先输入一个字符串（少于80个字符），将此字符串奇数位置的字符构成一个新的字符串并输出。

###测试说明

平台会对你编写的代码进行测试：

测试输入：123456
预期输出：
246

```c
#include<bits/stdc++.h>
using namespace std;
string s;int n;
int main() {
	getline(cin,s);n=s.size();
	for(int i=1;i<n;i+=2) putchar(s[i]);
    return 0;
}

```
## 5.20 任务名称

最长无重复字符串的长度

### 任务描述

本关任务：输入只包含小写字母的非空字符串，求最长无重复字母的字符串的长度

### 编程要求

根据提示，在右侧编辑器补充代码，输入只包含小写字母的非空字符串，长度小于100，寻找没有重复字母的子串，求这一类子串的最大长度并输出

### 测试说明
平台会对你编写的代码进行测试：

测试输入：abcabcbb
预期输出：
3
输出说明：子串abc长度为3

```c
#include<bits/stdc++.h>
using namespace std;
char s[103];
int n,mx,last[200],i,j;
int main() {
	for(cin>>s,n=strlen(s);j<n;++j) {
		i=max(i,last[s[j]]);
		mx=max(mx,j-i+1);
		last[s[j]]=j+1;
	}
	cout<<mx;
    return 0;
}
```
## 5.20

```c
#include <iostream>
using namespace std;
int n,l,a[100001],t=1,maxn,minn=1e9+7;
int main()
{   
    cin>>n>>l;
    for(int i=1;i<=n;++i){
        scanf("%d",&a[i]);
        if(t==1){
            maxn=max(maxn,l-a[i]);
            minn=min(minn,l-a[i]);
        }
        if(t==-1){
            maxn=max(maxn,a[i]);
            minn=min(minn,a[i]);
        }
        t=t*-1;
    }
    cout<<minn<<" "<<maxn;
    return 0;
}
```
## 5.21

```c    //by 辛统
#include <bits/stdc++.h>
using namespace std;
const int maxn = 1e8;
typedef long long ll;
int mp[10][10], a[10][10];
int count(int x){
    int p = 0;
    while(x) {p += x&1; x>>=1;}
    return p; 
}
void change(int x, int y) {
    mp[x][y] = 1-mp[x][y];
    mp[x][y-1] = 1-mp[x][y-1];
    mp[x][y+1] = 1-mp[x][y+1];
    mp[x-1][y] = 1-mp[x-1][y];
    mp[x+1][y] = 1-mp[x+1][y];
}
int search(int layer, int sum) {
    if(layer==6) {
        int x = 1;
        for(int i=1;i<=5;i++) x&=mp[5][i];
        if(x) return sum;
        else return maxn;
    }
    for(int i=1;i<=5;i++) {
        if(mp[layer-1][i]==0) {
            change(layer,i); sum++;
        }
    }
    return search(layer+1,sum);
}
int main() {
    char s[20];
    int ans = maxn;
    for(int i=1;i<=5;i++) {
        scanf("%s",s+1);
        for(int j=1;j<=5;j++) a[i][j] = s[j]-'0';
    }
    for(int state=0; state<=(1<<6)-1; state++) {
        for(int i=1;i<=5;i++)
            for(int j=1;j<=5;j++) mp[i][j]=a[i][j];
        for(int i=0;i<5;i++) {
            if((state>>i)&1) {
                change(1,i+1);
            }
        }
        ans = min(ans, search(2, count(state)));
    }
    if(ans==maxn) cout<<"-1";
    else cout<<ans;
}
```
## 5.22

```c    //by 李瑞
#include <iostream>
using namespace std;

int main()
{
    int n;
	cin >> n;
	cin.get();
	int i = 0;
	int num = 0;
	char ch[1000] ;
	cin.getline(ch, 1000);
	
	while (ch[i] != '\0')
	{
		++num;
		++i;
	}
	if (n == 1)
	{
		for (int j = 0; j < num; ++j)
		{
			cout << ch[j];
		}
	}
	else
	{
		int b = 2 * n - 2;

		int row;
		for (int h = 0; h*b < num; ++h)//第一行
		{
			cout << ch[h*b];
		}
		int flag = 1;
		for (row = 1; row < n - 1; ++row)
		{
			flag = 1;
			int c = b - 2 * row;
			int d = 2 * row;
			int sum = row;
			if (sum < num)
				cout << ch[sum];
			for (int h = 0; sum < num; ++h)
			{
				switch (flag)
				{
				case 1:sum += c; flag = 0; break;
				case 0:sum += d; flag = 1; break;
				}
				if (sum < num){cout << ch[sum];}
			}
		}
		for (int h = 0; n - 1 + b * h < num; ++h){cout << ch[n - 1 + b * h];}
	}
    return 0;
}
```
