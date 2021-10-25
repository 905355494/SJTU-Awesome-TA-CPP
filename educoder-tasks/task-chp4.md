# 实训作业参考答案 —— 第四章 循环程序设计




## 4.1 任务名称

X数

### 任务描述


编写一个程序，读入两个正整数a和b，并且a<=b, 计算并输出闭区间[a,b]中的X数。X数为各个数位上数字的立方和等于其自身的数字，例如：
153 = 1 * 1 * 1 + 5 * 5 * 5 + 3 * 3 * 3  // 153 is a X-number.
12 is not equal to 1 * 1 * 1 + 2 * 2 * 2  // 12 is not a X-number.
如果没有找到X数，输出提示信息no


### 编程要求

根据提示，在右侧编辑器补充代码，计算并输出[a,b]中的X数(以空格分隔)，或者输出no

### 代码样例

```cpp
#include <iostream>
using namespace std;

int main(void) {

    int a,b; cin >> a >> b;
    bool not_start = true;
    for (int i=a;i<=b && i<=1000;i++) {
        int s=0;
        for (int j=i;j;j/=10) s += (j%10)*(j%10)*(j%10);
        if (s == i) {
            if (!not_start) cout << ' ';
            cout << i;
            not_start = false;
        }
    }
    if (not_start) cout << "no";
    cout << endl;

    return 0;
}

```




## 4.2 任务名称

求a+aa+aaa+....+aa…aa（n个a）之和

### 任务描述


输入两个正整数a和n，求a+aa+aaa+....+aa…aa（n个a）之和。

### 测试说明


输入描述：两个正整数 a 和 n，(1<=a<=9, 1<=n<=8)，用空格分隔。
输出描述：输出答案。

样例输入：
2  5
样例输出：
24690

### 代码样例

```cpp
#include<iostream>
using namespace std;
int main()
{
    int a, n;
    cin >> a >> n;
    int ans = 0;
    for (int i=1;i<=n;i++) {
        int tmp = 0;
        for (int j=0;j<i;j++) tmp = tmp * 10 + a;
        ans += tmp;
    }
    cout << ans << endl;

    return 0;
}
```







## 4.3 任务名称

求斐波那契数列的第n项

### 任务描述

利用循环结构求解斐波那契数列的第 n 项。

斐波那契数列满足 fib[0]=0, fib[1]=1, fib[n]=fib[n-1]+fib[n-2]。


### 测试说明

输入描述：一个正整数n（1<=n<=80）。
输出描述：输出fib[n]。

样例输入：1
样例输出：1

### 代码样例

```cpp
#include<iostream>
using namespace std;
int main()
{
    int n; cin >> n;
    long long a = 1, b = 0;
    for (int i=2;i<=n;i++) {
        long long c = a + b;
        b = a;
        a = c;
    }
    cout << a << endl;

    return 0;
}
```




## 4.4 任务名称

求f10(n)的值

### 任务描述


本关任务：定义 f(n) 为 n 在十进制下的数位和。例如 f(123)=1+2+3=6, f(2048)=2+0+4+8=14。

定义 f<sub>1</sub>(n) = f(n)，f<sub>2</sub>(n)=f(f<sub>1</sub>(n))，f<sub>k</sub>(n) = f(f<sub>k-1</sub>(n)) (k>=2)。给定 n，求 f<sub>10</sub>(n)。


### 测试说明

输入描述：一个正整数 n(1<=n<=10^9)。
输出描述：输出 f10(n)。

样例输入：123456789
样例输出：9

### 代码样例

```cpp
#include <iostream>
using namespace std;

int main(void) {
    /** begin **/
    int n; cin >> n;
    int ans = 0;
    for (;n;n/=10) ans = (ans + n%10)%9;
    if (ans==0) ans = 9;
    cout << ans << endl;
    /**  end  **/

    return 0;
}
```




## 4.5 任务名称

实现欧几里得算法计算最大公约数

### 任务描述

两个整数 n,m 的最大公约数是能整除 n,m 的最大的整数，记为 gcd(n,m)。欧几里得算法给出了求最大公约数的一种快速的方法，它可以简单描述为

$$gcd(n,m) = gcd(m,n%m)$$

​	gcd(n,0) = n
请基于此实现欧几里得算法。

### 测试说明

输入描述：两个正整数n,m(1<=n,m<=10^9),中间用空格分隔。
输出描述：输出它们的最大公约数。

样例输入1：21 15
样例输出1：3

样例输入2：5 7
样例输出2：1

### 代码样例

```cpp
#include<iostream>
using namespace std;
int main()
{
    int n, m;
    cin >> n >> m;
    while (m) {
        int tmp = n%m;
        n = m;
        m = tmp;
    }
    cout << n << endl;

    return 0;
}

```

## 4.6 任务名称

求x+rev(x)=n的正整数解的个数

### 任务描述


本关任务：x为正整数，定义rev(x)是x在十进制下翻转得到的数（x无前导零），如rev(53)=35,rev(1200)=21。给定正整数n，求x+rev(x)=n的正整数解的个数。

### 编程要求

根据提示，在右侧编辑器补充代码，输入一个正整数n(1<=n<=100000)。输出方程解的个数。

### 测试说明

平台会对你编写的代码进行测试：

测试输入：1221
预期输出：3

### 代码样例

```cpp  //by 邓景熙
#include<bits/stdc++.h>
using namespace std;
int ans;
int rev(int x){
	int y=0;
	while(x){
		y=y*10+x%10;
		x/=10;
	}
	return y;
}
int main(){
	int n;
	cin>>n;
	for(int i=1;i<=n;i++)
		if(i+rev(i)==n)
            ans=ans+1;
	cout<<ans<<endl;
	return 0;
}
```

## 4.7 任务名称

第2大数

### 任务描述


本关任务：编写一个能找到第二大数的程序

### 编程要求

根据提示，在右侧编辑器补充代码，首先输入n，表示后面将输入n个数，然后输入n个整数，输出其中第二大的数。

### 测试说明

平台会对你编写的代码进行测试：

测试输入：5 0 8 3 8 6
预期输出：8

### 代码样例

```cpp
#include <iostream>
using namespace std;

int main()
{
    int n,a=0,b=0,x;
    cin>>n;

    for (int i=1;i<=n;i++){
        cin>>x;
        if (x>=a) b=a,a=x;
        else if (x>=b) b=x;
    }
    cout<<b<<endl;

    return 0;
}
```

## 4.8 任务名称

少了哪一个

### 任务描述


本关任务：找出输入的n个[0,n]范围内的不同整数缺少了哪一个。

### 编程要求

根据提示，在右侧编辑器补充代码，输入n，然后输入n个[0,n]之间的不同整数，找出[0,n]中哪个数没有输入，将其输出

### 测试说明

平台会对你编写的代码进行测试：

测试输入：3 0 1 3
预期输出：2

### 代码样例

```cpp
#include <iostream>
using namespace std;

int main()
{
    int n,x,sum;
    cin>>n;
    
    sum=n*(n+1)/2;
    for (int i=1;i<=n;i++){
        cin>>x;
        sum=sum-x;
    }
    cout<<sum<<endl;
        
    return 0;
}
```

## 4.9 任务名称

求出因子

### 任务描述


本关任务：编写一个能求出正整数n所有不同因子的程序

### 编程要求

根据提示，在右侧编辑器补充代码，输入正整数n，输出其所有不同因子

### 测试说明

平台会对你编写的代码进行测试：

测试输入：6
预期输出：1 2 3 6

### 代码样例

```cpp
#include <iostream>
using namespace std;

int main()
{
    int n;
    cin>>n;

    for (int i=1;i<=n;i++){
        if (n%i==0) cout<<i<<" ";
    }

    return 0;
}
```

## 4.10 任务名称

得到1

### 任务描述


本关任务：给定正整数n，对n执行任意次下列操作：
1）如果n是2的倍数，用n/2代替n
2）如果n是3的倍数，用2n/3代替n
3）如果n是5的倍数，用4n/5代替n
例如当n=30时，可以根据规则1变为15，或者根据规则2变为20，或者根据规则3变为24。
那么从n开始，通过执行上述操作最终是否可以得到1？如果可以得到1，那么最少需要多少次上述操作？

### 编程要求

根据提示，在右侧编辑器补充代码，输入正整数n，如果通过执行上述操作最终不可以得到1，输出-1，如果可以得到1，输出最少需要多少次上述操作

### 测试说明

平台会对你编写的代码进行测试：

测试输入：5
预期输出：3

### 代码样例

```cpp
#include <iostream>
using namespace std;

int main()
{
    int n,t=0;
    cin>>n;

    while (n!=1){
        if (n%2==0) n=n/2,t=t+1;
        else if (n%3==0) n=2*n/3,t=t+1;
        else if (n%5==0) n=4*n/5,t=t+1;
        else if (n!=1) {
            cout<<-1<<endl;
            break;
        }
    }
    if (n==1) cout<<t<<endl;

    return 0;
}
```

## 4.11 任务名称

爬楼梯

### 任务描述

本关任务：要走上一个有n级台阶的楼梯，你可以一次走一级，也可以一次走两级。计算有多少种走法。

### 编程要求

根据提示，在右侧编辑器补充代码，用户输入正整数n，计算并输出有多少种走法。

### 测试说明

平台会对你编写的代码进行测试：

测试输入：3
预期输出：3

### 代码样例

```cpp
#include <iostream>
using namespace std;

int a[100000];
int main()
{
    int i=2;
    a[0]=1;
    a[1]=1;
    for (i>=2;i<=100000;i++) a[i]=a[i-1]+a[i-2];
    int n;
    cin>>n;
    cout<<a[n]<<endl;

    return 0;
}

```

## 4.12 任务名称

求n！包含质因子p的数量

### 任务描述


本关任务：求n！包含质因子p的数量

### 编程要求

根据提示，在右侧编辑器补充代码，输入正整数n和素数p，输出n！包含质因子p的数量

### 测试说明

平台会对你编写的代码进行测试：

测试输入：6 2
预期输出：4
输出说明：6!=720=2*2*2*2*3*3*5

### 代码样例

```cpp
#include <iostream>
using namespace std;

int main()
{
    int n,p,num=0;
    cin>>n>>p;

    while (n>=p){
        num=num+n/p;
        n=n/p;
    }
    cout<<num<<endl;

    return 0;
}
```

## 4.13 任务名称

寻找素数

### 任务描述


本关任务：输入两个正整数m和n（m≤n），编写一个程序，统计并输出m～n之间（包含m和n）的素数的个数。

### 编程要求

根据提示，在右侧编辑器补充代码，输入两个正整数m和n（m≤n），计算并输出素数的个数。

### 测试说明

平台会对你编写的代码进行测试：

测试输入：1 10
预期输出：4

### 代码样例

```cpp  //by 王一舟
#include <iostream>
using namespace std;

int main()
{
    int m,n,num=0,s,y;
    cin>>m>>n;

    for (int i=m;i<=n;i++){
        s=2,y=0;
        while (s*s<=i){
            if (i%s==0) y=y+1;
            s++;
        }
        if (y==0 && i!=1) num++;

    }
    cout<<num<<endl;

    return 0;
}
```

## 4.14 任务名称

冰雹猜想

### 任务描述


本关任务：给出一个正整数 n，然后对这个数字一直进行下面的操作：如果这个数字是奇数，那么将其乘 3 再加 1，否则除以 2。经过若干次循环后，最终都会回到 1。经过验证，很大的数字都可以按照这样的方式变成 1，所以被称为“冰雹猜想”。例如：当 n 是 20，变化的过程是 [20, 10, 5, 16, 8, 4, 2, 1]； 而当 n 是 1 的时候，变化的过程是 [1]。根据给定的数字 n，验证这个猜想，即输出整个变化序列。

### 编程要求

根据提示，在右侧编辑器补充代码，输入正整数n，计算并输出整个数字序列。

### 测试说明

平台会对你编写的代码进行测试：

测试输入：20
预期输出：20 10 5 16 8 4 2 1

### 代码样例

```cpp
#include <iostream>
using namespace std;

int main()
{
    int n;
    cin>>n;

    while (n!=1){
        cout<<n<<" ";
        if (n%2==1) n=3*n+1;
        else n=n/2;
    }
    cout<<1<<endl;
    return 0;
}
```

## 4.15 任务名称

最大的三位数因子

### 任务描述

本关任务：从键盘任意输入一个数n （1000 <= n <= 1000000），编程计算并输出n的所有约数中最大的一个三位数（即最大的三位约数）。如果n小于1000或者大于1000000，则输出“Input error!”。如果没有三位数的约数，则输出“Not found!”。

### 编程要求

根据提示，在右侧编辑器补充代码，输入整数n，输出n的所有约数中最大的一个三位数（即最大的三位约数）。如果n小于1000或者大于1000000，则输出“Input error!”。如果没有三位数的约数，则输出“Not found!”。

### 测试说明

平台会对你编写的代码进行测试：

测试输入：1000
预期输出：500

### 代码样例

```cpp  by 李瑞
#include <iostream>
using namespace std;

int main()
{
int n;
	cin >> n;
	int i = 999;
	int m = 0;
	if (n < 1000 || n>1000000)
		cout << "Input error!";
	else
	{
		for (; i >= 100; --i)
		{
			if (n%i == 0)
			{
				m = i;
				break;
			}
		}
		if (m == 0)
			cout << "Not found!";
		else
			cout << m;
	}
    return 0;
}
```

## 4.16 任务名称

求x的平方根的整数部分

### 任务描述


本关任务：编写一个能计算x的平方根的整数部分的程序

### 编程要求

根据提示，在右侧编辑器补充代码，输入正整数x，输出x的平方根的整数部分，不得使用数学库，并且考虑如何减少计算量。

### 测试说明

平台会对你编写的代码进行测试：

测试输入：8
预期输出：2

### 代码样例

```cpp
#include <iostream>
using namespace std;

int main()
{
int x;
	cin >> x;
	int n = x;
	for (; n >= 1; --n)
	{
		if (x/n>=n)
		{
			cout << n;
			break;
		}
	}
    return 0;
}
```

## 4.17 任务名称

2的幂

### 任务描述

本关任务：判断输入的正整数n是否为2的幂

### 编程要求

根据提示，在右侧编辑器补充代码，输入正整数n，输出判断结果true或false

### 测试说明

平台会对你编写的代码进行测试：

测试输入：16
预期输出：true

### 代码样例

```cpp
#include <iostream>
using namespace std;

int main()
{
    int n;
    cin>>n;

    while (n%2==0){
        n=n/2;
    }
    if (n==1) cout<<"true"<<endl;
    else cout<<"false"<<endl;

    return 0;
}
```

## 4.18 任务名称

最少纸币数量

### 任务描述

本关任务：目前的纸币系统包含5种纸币，为1元、5元、16元、23元和33元，输入要购买物品的价格n为1～99元的整数，则购买该价格的物品最少需要几张纸币呢？分别给出穷举法和贪心算法的结果

### 编程要求

根据提示，在右侧编辑器补充代码，用户输入物品价格n，计算并输出2个结果，分别代表穷举法的结果和贪心法的结果

### 测试说明

平台会对你编写的代码进行测试：

测试输入：4
预期输出：4 4

### 代码样例

```cpp //by 罗锦润
#include<bits/stdc++.h>
using namespace std;
const int m[]={1,5,16,23,33};
int n,f[200],g;
int main() {
	cin>>n;
	memset(f,0x3f,sizeof(f));
	for(int i=0;i<5;++i) f[m[i]]=1;
	for(int i=1;i<n;++i)
		for(int j=0;j<5;++j)
			f[i+m[j]]=min(f[i+m[j]],f[i]+1);
	cout<<f[n]<<' ';
	for(int i=4;n;n%=m[i--]) g+=n/m[i];
	cout<<g;
    return 0;
}
```

## 4.19 任务名称

完全数

### 任务描述


本关任务：完全数（perfect number），又称为完美数或完备数，是一些特殊的自然数。它所有的真因子（即除了自身以外的约数）的和，恰好等于它本身。例如：28是一个完全数，它有约数1、2、4、7、14、28，除去它本身28外，其余5个数相加：1+2+4+7+14=28

### 编程要求

根据提示，在右侧编辑器补充代码，输入两个正整数m和n，输出m ~ n之间（包含m和n）的所有完全数。如果m ~ n之间没有完全数，则输出-1

### 测试说明

平台会对你编写的代码进行测试：

测试输入：1 100
预期输出：6 28

### 代码样例

```cpp
#include <iostream>
using namespace std;

int main()
{
    int m,n,a,add,num=0,x;
    cin>>m>>n;

    x=m;
    while (x>=m && x<=n){
            add=0;
            for (a=x/2;a>=1;a--){
                if (x%a==0) add=add+a;
            }
            if (add==x) cout<<x<<" ",num=num+1;
            x=x+1;
        }


    if (num==0) cout<<"-1"<<endl;


    return 0;
}
```




## 4.20 任务名称

指定数字的个数

### 任务描述

本关任务：从键盘输入一个正整数 number，求其中含有指定数字 digit 的个数。例如输入正整数 number=1222 ,若 digit=2 ，则 1222 中含有 3 个 2。

### 编程要求

根据提示，在右侧编辑器补充代码，从键盘输入正整数 number 和 digit，计算并输出指定数字的个数

### 测试说明

测试输入：1222 2
预期输出：3

### 代码样例

```cpp
#include <iostream>
using namespace std;

int main()
{
    int number,digit,n=0;
    cin>>number>>digit;

    while (number>0){
        if (number%10==digit) n=n+1;
        number=number/10;
    }
    cout<<n<<endl;

    return 0;
}
```



## 4.21 任务名称

画菱形

### 任务描述

本关任务：输入n，画一个2n-1行的菱形

### 编程要求

根据提示，在右侧编辑器补充代码，输入正整数n，输出一个2n-1行的菱形

### 测试说明

平台会对你编写的代码进行测试：

测试输入：3
预期输出：
  +
 +++
+++++
 +++
  +

### 代码样例

```cpp  //by 辛统
#include <bits/stdc++.h>
using namespace std;
typedef long long ll;
char s[100000];
int main() {
    int n; scanf("%d",&n);
    for(int i=1;i<=n;i++) {
        int t = n-i;
        for(int j=1;j<=t;j++)
            printf(" ");
        for(int j=1;j<=2*i-1;j++) {
            printf("+");
        }
        puts("");
    }

}
```



## 4.22 任务名称

统计数字

### 任务描述

本关任务：读入一系列整数，统计正整数和负整数的个数，读入0表示结束

### 编程要求

根据提示，在右侧编辑器补充代码，用户输入入一系列整数，输入0表示结束，统计正整数和负整数的个数并输出

### 测试说明

平台会对你编写的代码进行测试：

测试输入：1 2 3 -1 -2 0
预期输出：
3 2

### 代码样例

```cpp
#include <iostream>
using namespace std;

int main()
{
    int m=0,n=0,x;

    cin>>x;
    while (x!=0){
        if (x>0) m=m+1;
        else n=n+1;
        cin>>x;
    }
    cout<<m<<" "<<n<<endl;

    return 0;
}
```