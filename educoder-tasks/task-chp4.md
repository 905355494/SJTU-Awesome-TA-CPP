# 实训作业参考答案 —— 第四章 循环程序设计



## 4.1 任务名称

今天星期几

### 任务描述


本关任务：已经知道2000年1月1日是星期六。设计一个循环，输入一个新的日期，计算星期几。

### 编程要求

根据提示，在右侧编辑器补充代码，计算给定的日期是星期几（星期1~星期7）。

### 测试说明

平台会对你编写的代码进行测试：

测试输入：`2020 9 28`；
预期输出：`星期1`

### 代码样例

```cpp
#include <iostream>
using namespace std;

int main(void) {
    int y = 2000, m = 1, d = 1, w = 6, yy, mm, dd;
    cin >> yy >> mm >> dd;
    for (;;) {
        if (y==yy && m==mm && d==dd) {
            cout << "星期" << w << endl;
            break;
        }
        d++;
        if (((m==1 || m==3 || m==5 || m==7 || m==8 || m==10 || m==12) && d>31)
            || ((m==4 || m==6 || m==9 || m==11) && d>30)
            || (m==2 && (d > 28+((y%4==0 && y%100!=0) || (y%400==0)))))
            m++, d=1;
        if (m > 12) y++, m=1;

        w++;
        if (w == 8) w = 1;
    }
    return 0;
}
```





## 4.2 任务名称

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





## 4.3 任务名称

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





## 4.4 任务名称

改错题

### 任务描述


本关任务：计算下列式子的和，当最后一项的值小于 $$10^{-6}$$ 时结束。

$$e=1+\frac1{1!}+\frac1{2!}+\frac1{3!}+⋯+\frac1{n!}$$
以下代码是有错的源程序，请进行改正。
代码清单：
```
#include<iostream>
#include<iomanip>
using namespace
std;

const double EPS = 1E-6;

int main() {
    int i, n, item;
    double e;

    e = 1;
    n = 1;
    item = 1;
    do {
        for (i = 1; i <= n; i++)
            item *= i;
            e += 1 / item;
            n++;
    } while (item >= EPS);

    cout <<”e =”<<fixed << setprecision(6) << e << endl;

    return 0;
}
```

### 测试说明

输入描述：无。
输出描述：输出程序运行结果。

### 代码样例

```cpp
#include<iostream>
#include<iomanip>
using namespace std;
const double EPS = 1E-6;
int main() {
    int i, n, item;
    double e;
    e = 1;
    n = 1;
    item = 1;
    do {
        item = 1;
        for (i = 1; i <= n; i++)
            item *= i;
        e += 1.0 / item;
        n++;
    } while (item >= EPS);
    cout <<fixed << setprecision(6) << e << endl;
    return 0;
}
```



## 4.5 任务名称

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





## 4.6 任务名称

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





## 4.7 任务名称

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



## 4.8 任务名称

求x+rev(x)=n的正整数解的个数

### 任务描述


x为正整数，定义rev(x)是x在十进制下翻转得到的数（x无前导零），如rev(53)=35,rev(1200)=21。给定正整数n，求x+rev(x)=n的正整数解的个数。


### 测试说明
输入描述：一个正整数n(1<=n<=100000)。
输出描述：输出答案。

样例输入：1221
样例输出：3
样例解释：三个解为x=1020,1110,1200

### 代码样例

```cpp
#include<iostream>
using namespace std;
int main()
{
    int n; cin >> n;
    int ans = 0;
    for (int i=1;i<=n;i++) {
        int rev = 0;
        for (int _i=i;_i;_i/=10) rev = rev*10+_i%10;
        if (rev + i == n) ans++;
    }
    cout << ans << endl;

    return 0;
}
```



## 4.9 任务名称

求能带走的物品最大总价值

### 任务描述


假设有 n 件物品，物品 i 价值 i 美元，重量为 1 磅，小明的背包最多只能携带 W 磅重量，但他想买尽可能多地贵重物品。求他能带走的物品最大总价值。

### 测试说明


输入描述：第一行两个正整数n,W(n<=100, W<=100)。
输出描述：输出最大总价值。


> 每行的数字之间用空格分隔。

样例输入：3 2
样例输出：5

### 代码样例

```cpp
#include<iostream>
using namespace std;
int main()
{
    int n, W;
    cin >> n >> W;
    int ans = 0;
    for (int i=0;i<W && i<n;i++)
        ans += n-i;
    cout << ans << endl;

    return 0;
}
```



