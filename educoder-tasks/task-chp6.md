# 实训作业参考答案 —— 第六章 过程的封装：函数（上、下）



## 6.1 任务名称

判断素数

### 任务描述


本关任务：输入两个正整数m和n（$$1\leq m \leq n\leq100$$），编写一个程序，统计并输出m～n之间（包含m和n）的素数的个数。

### 编程要求

定义并调用函数 `isPrime(n)` 来判断n是否是素数。

### 测试说明

平台会对你编写的代码进行测试：

测试输入：`1 10`；
预期输出：
`4`

测试输入：`40 50`；
预期输出：
`3`

提示：
对于数n，判断它是否是素数，不必枚举 [2，n-1] 之间的数，只需要枚举[2,$$\sqrt n$$]之间的数即可。

### 代码样例

```cpp
#include<iostream>
using namespace std;

bool isPrime(int n)
{
    /** Begin **/
    if (n == 1) return false;
    for (int i=2;i*i<=n;i++) if (n%i==0) return false;
    return true;
    /**  End  **/
}

int main()
{
    int m, n;
    cin >> m >> n;

    /** Begin **/
    int ans = 0;
    for (int i=m;i<=n;i++) ans += isPrime(i);
    cout << ans << endl;

    /**  End  **/
    return 0;
}
```





## 6.2 任务名称

完全数

### 任务描述


完全数（perfect number），又称为完美数或完备数，是一些特殊的自然数。它所有的真因子（即除了自身以外的约数）的和，恰好等于它本身。例如：28是一个完全数，它有约数1、2、4、7、14、28，除去它本身28外，其余5个数相加：1+2+4+7+14=28.

编写程序，输入两个正整数m和n($$1\leq m\leq n\leq 10000$$)，输出m ~ n之间（包含m和n）的所有完全数。如果m ~ n之间没有完全数，则输出-1.


### 编程要求

定义并调用函数 `perfectNumber(n)` 判断 n 是否是完全数。

### 测试说明

平台会对你编写的代码进行测试：

测试输入：`100 10000`；
预期输出：
`496 8128`

测试输入：`100 200`；
预期输出：
`-1`

### 代码样例

```cpp
#include<iostream>
using namespace std;

bool perfectNumber(int n)
{
	/** Begin **/
    int sum = 0;
    for (int i=1;i<n;i++) if (n%i==0) sum += i;
    return sum == n;
    /**  End  **/
}

int main()
{
    int m, n;
    cin >> m >> n;
    /** Begin **/
    int f = 0;
    for (int i=m;i<=n;i++) {
        if (perfectNumber(i)) cout << i << " ", f = 1;
    }
    if (!f) cout << -1;
    /**  End  **/

    return 0;
}
```





## 6.3 任务名称

进制转换

### 任务描述

输入两个十进制正整数 n 和 base($$2\leq base\leq16$$)，将 n 转换为 base 进制后输出。


### 相关知识


为了完成本关任务，你需要掌握：1.如何将十进制数转换成 base 进制数。

#### 进制转换
思考十进制向二进制转换的方法：除2取余，那么将十进制数转换成 base 进制数只需要重复“除base取余”。

大于十进制的 base 进制常用的是十六进制，在十六进制中，除了十进制中用到的 0-9 这十个数字外，还引入了A、B、C、D、E、F 来分别表示十进制的10、11、12、13、14、15.


### 编程要求

定义并调用函数 `printInt(n,base)`，它的功能是输出 n 的 base 进制

### 测试说明

平台会对你编写的代码进行测试：

测试输入：`255 16`；
预期输出：
`FF`

测试输入：`128` `2`；
预期输出：
`10000000`

提示：可以利用A、B、C、D、E、F 来分别表示十进制中的10、11、12、13、14、15.

### 代码样例

```cpp
#include<iostream>
using namespace std;

const int MAX = 1000;
void printInt(int n,int base)
{
    // write your code here
    static char num[20] = "0123456789ABCDEF";
    int a[MAX];
    for (a[0]=0; n; n/=base) a[++a[0]] = n%base;
    for (;a[0];) cout << num[a[a[0]--]];
}

int main()
{
    int n, base;
    cin >> n >> base;
    printInt(n, base);
    return 0;
}
```





## 6.4 任务名称

冰雹猜想

### 任务描述


给出一个正整数 n$$(n\le 100)$$，然后对这个数字一直进行下面的操作：如果这个数字是奇数，那么将其乘 3 再加 1，否则除以 2。经过若干次循环后，最终都会回到 1。经过验证，很大的数字（$$7\times10^{11}$$）都可以按照这样的方式变成 1，所以被称为“冰雹猜想”。例如：当 n 是 20，变化的过程是 [20, 10, 5, 16, 8, 4, 2, 1]； 而当 n 是 1 的时候，变化的过程是 [1].

根据给定的数字 n，验证这个猜想，即输出整个变化序列。

### 编程要求

定义并调用函数 `valid(n)`，输出“冰雹猜想”的整个变化序列。

### 测试说明

平台会对你编写的代码进行测试：

测试输入：`20`
预期输出：
`20 10 5 16 8 4 2 1`

测试输入：`68`
预期输出：
`68 34 17 52 26 13 40 20 10 5 16 8 4 2 1`

### 代码样例

```cpp
#include<iostream>
using namespace std;

void valid(int n)
{
    /** Begin **/
    cout << n << " ";
    while (n>1) {
        cout << (n=n%2?3*n+1:n/2) << " ";
    }
    /**  End  **/
}

int main()
{
    int n;
    cin >> n;
    valid(n);
    return 0;
}
```



## 6.5 任务名称

最大值和最小值

### 任务描述


本关任务：编写函数模板maxmin，可以得到并输出数组中最大数和最小数，再编写一个main函数，通过调用你所设计的函数模板来展现对不同类型数组的处理情况


### 相关知识


为了完成本关任务，你需要掌握：1.模板函数，2.如何遍历数组。

### 编程要求

程序将输入四行，需要通过输入信息分别产生两个数组：
m
a1 a2 ... am
n
b1 b2 ... bn
其中[a1...an]是一个整型数组，[b1...bn]是一浮点数 数组，m和n是两个整数，分别代表两个数组的长度。

输出格式为
`整型数组最大值 最小值`
`浮点数组最大值 最小值`
### 测试说明

平台会对你编写的代码进行测试：

测试输入：
`4`
`1 2 3 4`
`5`
`5.0 4.0 3.0 2.0 1.0`
预期输出：
`4 1`
`5 1`

### 代码样例

```cpp

```





## 6.6 任务名称

潜泳问题

### 任务描述
某单位在某个湖里举行潜水比赛，这是一个团体项目，每一支队伍由n人组成，要求所有队员从A岸潜水到B岸。在潜水过程中必须用氧气瓶，但每支队伍只有一个氧气瓶。最多两个人同时使用一个氧气瓶，但此时两人必须同步前进，因此到达终点的时间等于较慢的一人单独从A到B的时间。大家都很Nice，随便两个人都愿意共用一个氧气瓶有用。请安排一种策略，让最后一名队员尽早到达终点。

### 编程要求

编写程序，首先输入队伍人数n（n < 1000），接着是n个队员单独游到终点所用的时间。要求输出所有队员最早到达终点的时间。

### 相关知识
可以通过sort函数对数组进行排序，需要用到的头文件已经给出。例如
```
int a[] = {5,4,3,2,1};
sort(a,a+5);
// 输出a将得到12345
```

### 测试说明

平台会对你编写的代码进行测试：

测试输入：
`3`
`1`
`3`
`4`
预期输出：
`8`

### 提示
首先将n各队员游到重点耗时长短按递增排序，得到
$$P_1 P_2 ... P_n$$
我们把A岸耗时最长的两个人$$P_n, P_{n-1}$$游到B岸看成一个步骤。为了达到耗时最短，需要在如下两种方案中选择。

方案1：安排耗时最短的两个人$$P_1, P_2$$先游到B岸，然后$$P_1$$游回A岸，接着安排耗时最长的两个人$$P_n,P_{n-1}$$游到B岸，再安排$$P_2$$游回A岸，总耗时$$t_1 = 2*P_2 + P_1 + P_n$$.

方案2：安排耗时最短和最长的$$P_1,P_n$$先游到B岸，$$P_n$$留在B岸，$$P_1$$回A岸。然后$P_1,P_{n-1}$游到B岸，再安排$$P_1$$游回A岸。总时间为$$t_2 = 2*P_1 + P_n + P_{n-1}$$，

如果$$t_1 < t_2 $$,就选择方案一，否则方案二。重复上述策略，直到所有人到达B。算法实现时需要考虑人数就。如果是奇数，最后在A岸剩下人为$$P_1, P_2,P_3$$,3人到达B岸耗时$$P_1 + P_2 +P_3$$,如果是偶数，最后剩下两人为$$P_1,P_2$$,耗时$$P_2$$.

简单来说，每个阶段运两个人过去有两种贪心原则：

1.用耗时最少的每次运一个走，

2.用耗时最少的和次少的分两次次运走耗时最多的两个走。

每次在两种贪心原则中，选择最优的。这道题的策略就是两种贪心优中选优。

### 代码样例

```cpp
#include <iostream>
using namespace std;

void sort(int a[], int n)
{
    // sort a[]
    // write your code here
    for (int i=1;i<=n;i++)
        for (int j=1,tmp;j<=n-i;j++) if (a[j]>a[j+1])
            tmp = a[j], a[j] = a[j+1], a[j+1] = tmp;
}
int main()
{
   	// write your code here
    int n; cin >> n;
    int * a = new int [n+1];
    for (int i=1;i<=n;i++) cin >> a[i];
    sort(a, n);
    int ans = 0;
    for (int i=n;i>1;i-=2) {
        if (i == 2) ans += a[2];
        else if (i == 3) ans += a[1]+a[2]+a[3];
        else if (2*a[2]+a[1]+a[i] < 2*a[1]+a[i]+a[i-1])
            ans += 2*a[2]+a[1]+a[i];
        else ans += 2*a[1]+a[i]+a[i-1];
    }
    cout << ans << endl;
    return 0;
}
```



## 6.7 任务名称

Fibonacci函数

### 任务描述


本关任务：设计函数fib，每调用一次就返回Fibonacci数列的下一个值，即第一次调用返回1，第二次调用返回1，第三次调用返回2，第四次调用返回3……

要求：**不得使用全局变量**。

### 编程要求

根据提示，在右侧编辑器补充代码，编写一个函数fib()，使结果符合要求。

### 测试说明

平台会对你编写的代码进行测试：

测试输入：无；
预期输出：
`1`
`1`
`2`
`3`
`5`
`8`
`13`
`21`
`34`
`55`

### 注意

此题在后台会人工重新评判，请各位严格按照题目要求编写。

### 代码样例

```cpp
#include<iostream>
using namespace std;

int fib()
{
    //write your code here
    static int a = 1, b = 0;
    int c = a + b;
    b = a, a = c;
    return b;
}
int main()
{
    for (int i = 0; i < 10; i++)
        cout << fib() << endl;
    return 0;
}
```



## 6.8 任务名称

组合数

### 任务描述


本关任务：编写一个求n!的函数，并用于求从n个数中取m个数的组合数（m<=n）。


### 相关知识


组合数=n!/(m!*(n-m)!) 。

### 编程要求

根据提示，在右侧编辑器补充代码，使之符合要求。

### 测试说明

平台会对你编写的代码进行测试，每个测试样例的输入包括两个数字，第一个n，第二个是m：

测试输入：
`4 1`
预期输出：
`4`


测试输入：
`2 3`
预期输出：
`wrong!`

测试输入：
`3 2`
预期输出：
`3`

### 代码样例

```cpp
#include<iostream>
using namespace std;

long long factorial(int n)
{
    // write your code here
    long long ans=1;
    for (int i=1;i<=n;i++) ans = ans * i;
    return ans;
}

int main()
{
    // write your code here
    int n, m; cin >> n >> m;
    cout << factorial(n)/factorial(m)/factorial(n-m) << endl;
    return 0;
}
```



## 6.9 任务名称

计算谐均值

### 任务描述


两数值的谐均值可以这样计算：首先对两数值的倒数取平均值，最后再取倒数。编写一个带有两个double参数的函数，计算这两个参数的谐均值。函数原型为：
double Calculate(double x,double y);

例如，当$$x=3,y=4$$时，则谐均值的为
$$1/((1/x+1/y)/2) = 3.429$$


### 编程要求

根据提示，补全函数，并返回输入值的谐均值。

### 测试说明

平台会对你编写的代码进行测试,先输入测试样例数t，然后输入t组输入，程序依次输出t个谐均值。

测试输入：
`1`
`3 4`
预期输出：
`3.429`

测试输入：
`2`
`3 4`
`6.5 3.8`
预期输出：
`3.429`
`4.796`

### 代码样例

```cpp
#include <iostream>
#include <iomanip>
using namespace std;

double Calculate(double x,double y)
{
    // write your code here
    return 2/(1/x+1/y);
}

// 请不要修改main函数
int main()
{
    int t;
    cin >> t;
    while (t--) {
      	double x, y;
    	cin >> x >> y;
          cout << fixed << setprecision(3) << Calculate(x,y) << endl;
    }
    return 0;
}
```



## 6.10 任务名称

魔术师猜数

### 任务描述

在一种室内互动游戏中，魔术师要每位观众心里想一个三位数abc（a、b、c分别是百位、十位和个位数字），然后魔术师让观众心中记下acb、bac、bca、cab、cba五个数以及这5个数的和值。只要观众说出这个和是多少，则魔术师一定能猜出观众心里想的原数abc是多少。例如，观众甲说他计算的和值是1999，则魔术师立即说出他想的数是443，而观众乙说他计算的和值是1998，则魔术师说：“你算错了！”。请编程模拟这个数字魔术游戏。要求用函数实现，函数原型为：int Magic(int m);
其中形参m代表观众计算的和值。

### 编程要求

补全Magic函数，如果观众计算错误，请返回-1。另外请不要修改main函数。

### 测试说明

平台会对你编写的代码进行测试。测试数据包含t+1行，第一行是测试次数t，随后t行中每行输入一个m值，程序需要计算输出t个结果。

测试输入：
`1`
`1999`
预期输出：
`The number is 443`

测试输入：
`2`
`1999`
`1998`
预期输出：
`The number is 443`
`The sum you calculated is wrong!`

### 代码样例

```cpp
#include <iostream>

using namespace std;


int Magic(int m){
   /***********begin************/
   for (int x = 222-m%222; x < 1000; x += 222) {
       if (222*(x/100+x/10%10+x%10) == m + x) return x;
   }
   return -1;
   /***********end**************/
}

int main()
{
    int t,m;
    cin >> t;
    while(t--){
        cin >> m;
        int res = Magic(m);
        if(res == -1) {
            cout << "The sum you calculated is wrong!\n";
        } else {
            cout << "The number is " << res << endl;
        }
    }
}
```





## 6.11 任务名称

计算最大的三位约数

### 任务描述


本关任务：从键盘任意输入一个数n（1000<=n<=1000000），编程计算并输出n的所有约数中最大的一个三位数（即最大的三位约数）。如果n小于1000或者大于1000000，则输出“Input error!”。如果没有三位数的约数，则输出“Not found!”。

函数原型：int Func(int n)；
函数功能：计算n的所有约数中最大的三位数

### 编程要求

根据提示，在右侧编辑器补充代码，编写函数使之符合要求。

### 测试说明

平台会对你编写的代码进行测试：

测试输入：
`555555`
预期输出：
`777`

测试输入：
`1000`
预期输出：
`500`

测试输入：
`800`
预期输出：
`Input error!`

测试输入：
`121123`
预期输出：
`Not found!`

### 代码样例

```cpp
#include<iostream>
using namespace std;

int Func(int n)
{
    // start your code here
    for (int i=999;i>=100;i--) if (n%i==0) return i;
    return -1;
}

int main()
{
    // start your code here
    int n; cin >> n;
    if (n < 1000 || n > 1000000)
        cout << "Input error!\n";
    else {
        int res = Func(n);
        if (~res) cout << res << '\n';
        else cout << "Not found!\n";
    }
    return 0;
}
```





## 6.12 任务名称

统计正整数中指定数字的个数

### 任务描述

从键盘输入一个正整数 `number`，求其中含有指定数字 `digit` 的个数。

例如：从键盘输入正整数 `number=1222` ,若 `digit=2` ，则 `1222` 中含有 3 个 `2`。

### 编程要求

用函数实现，函数原型为：`int CountDigit(int number,int digit)`

### 测试说明

平台会对你编写的代码进行测试：

测试输入：`1222 2`
预期输出：`3`

测试输入：`1234 6`；
预期输出：`0`

### 代码样例

```cpp
#include<iostream>
using namespace std;

int CountDigit(int number,int digit)
{
    /** Begin **/
    int ans = 0;
    while (number) ans += (number%10==digit), number/=10;
    return ans;
    /**  End  **/
}

int main()
{
    int number, digit;
    cin >> number >> digit;
    cout << CountDigit(number,digit) <<endl;

    return 0;
}
```





## 6.13 任务名称

摘苹果

### 任务描述


陶陶家的院子里有一棵苹果树，每到秋天树上就会结出 `n` （$$1 \le n \le 100$$） 个苹果。苹果成熟的时候，陶陶就会跑去摘苹果。陶陶有个 30cm 高的板凳，当他不能直接用手摘到苹果的时候，就会踩到板凳上再试试。

现在已知每个苹果到地面的高度 `a[i]` cm（$$1\le i \le n$$，$$100 \le a[i]\le 200$$），以及陶陶把手伸直时能达到的最大高度 `height` cm （$$100 \le height \le 120$$），请你编写程序帮助陶陶计算一下他能摘到的苹果数目。

假设只要他能够伸手碰到苹果，苹果就会掉下来。

### 编程要求

调用函数 `int GetApple(int a[], int height, int n)`来计算淘淘能摘到的苹果数目。

函数参数：数组 `a` 保存苹果到地面的高度，`height` 代表陶陶把手伸直时能达到的最大高度，`n`为树上总的苹果数。

函数返回值：淘淘能摘到的苹果数目

### 测试说明

平台会对你编写的代码进行测试：

测试输入：
`10`
`100 200 150 140 129 134 167 198 200 111`
`110`
预期输出：
`5`

说明：第一行输入的数据是苹果数目`n`；第二行输入的数据是这`n`个苹果，每个苹果到地面的高度；第三行输入的数据是陶陶把手伸直时能达到的最大高度。

### 代码样例

```cpp
#include<iostream>
using namespace std;

int GetApple(int a[], int height, int n)
{
    int ans = 0;
    for (int i=1;i<=n;i++) if (height + 30 >= a[i]) ans++;
    return ans;
}

int main()
{
    int n, height, *a;
    cin >> n;
    a = new int[n+1];
    for (int i=1;i<=n;i++) cin >> a[i];
    cin >> height;

    cout << GetApple(a, height, n) << endl;

    delete [] a;
    return 0;
}

```



## 6.14 任务名称

孔融分梨

### 任务描述


孔融没有兄弟姐妹，到了周末，就找堂兄孔明、堂姐孔茹、堂弟孔伟等7个堂兄妹来到家里玩。孔融妈妈买了8个梨给孩子们吃，结果小黄狗桐桐淘气叼走了一个，大花猫鑫鑫偷偷藏了一个。孔融抢过剩下的6个梨，妈妈止住他，说他要和大家平分吃。孔融不高兴，说8个人怎么分6个梨？妈妈说可以用分数解决这个问题。孔融学过分数，说把每个梨切8个相等的块，每个人拿6块就行了。妈妈说不用切那么多块，每个梨切4个相等的块，每个人拿3块正好。孔融糊涂了。孔明说，我来教你。于是孔明给孔融讲起了分数的化简。

分数化简要化简到最简形式，比如12/20可以化简成6/10和3/5，但3/5是最简形式；100/8可以化简成 50 /4和 25 /2 , 而25/2 为最简形式。为了降低难度，不要求将假分数（如7/2）化简成带分数（3(1/2))形式。请编程帮助孔融将任意一个分数化简成最简形式。先从键盘输入两个整数m和n(1<=m,n<=10000) ，其中m表示分子，n表示分母。然后输出分数化简后的最简形式。

函数原型：int Gcd(int a, int b);
函数功能：计算a和b的最大公约数，输入数据超出有效范围时返回-1。


### 编程要求

根据提示，在右侧编辑器补充代码，编写函数使之符合要求。

### 测试说明

平台会对你编写的代码进行测试：

测试1:
测试输入：
`8 14` 
测试输出：
`4/7`

测试2:
测试输入：
`-13 31` 
测试输出：
`Input error!`

测试3:
测试输入：
`7 0`
测试输出：
`Input error!`

测试4:
测试输入：
`210 35` 
测试输出：
`6/1`

### 代码样例

```cpp
#include <iostream>
#include <cassert>
using namespace std;

int Gcd(int m, int n)
{
    // write your code here
    for (int i=m;i>=1;i--)
        if (n%i==0 && m%i==0) return i;

    assert(0);
}

int main()
{
    int m, n, ans;
    cin >> m >> n;

    // write your code here
    int g = Gcd(m, n);
    cout << m/g << '/' << n/g << endl;
    return 0;
}
```





## 6.15 任务名称

递归法计算两个数的最大公约数

### 任务描述


本关任务：编写一个用递归法计算两个数的最大公约数的程序。


### 编程要求

利用最大公约数的性质计算。对正整数a和b，当a>b时，若a中含有与b相同的公约数，则a中去掉b后剩余的部分a-b中也应含有与b相同的公约数，对a-b和b计算公约数就相当于对a和b计算公约数。反复使用最大公约数的上述性质，直到a和b相等为止，这时，a或b就是它们的最大公约数。这三条性质，也可以表示为： 
+ 性质1  如果a>b，则a和b与a-b和b的最大公约数相同，即Gcd(a, b) = Gcd(a-b, b)
+ 性质2  如果b>a，则a和b与a和b-a的最大公约数相同，即Gcd(a, b) = Gcd(a, b-a)
+ 性质3  如果a=b，则a和b的最大公约数与a值和b值相同，即Gcd(a, b) = a = b


根据提示，在右侧编辑器补充代码，计算并输出最大公约数。

### 测试说明

平台会对你编写的代码进行测试：

测试输入：`16`  `24`
预期输出：
`8`

测试输入：`-2`  `-8`
预期输出：
`Input error!`

### 代码样例

```cpp
#include<iostream>
using namespace std;

int Gcd(int a, int b)
{
    // write your code here
    if (a > b) return Gcd(a-b, b);
    if (b > a) return Gcd(a, b-a);
    return a;
}

int main()
{
    // write your code here
    int a, b; cin >> a >> b;
    cout << Gcd(a, b) << endl;
    return 0;
}
```





## 6.16 任务名称

递归法计算游戏人员的年龄

### 任务描述


本关任务：编写一个使用递归法计算游戏人员年龄的小程序。

有n个人围坐在一起，问第n个人多大年纪，他说比第n-1个人大2岁；问第n-1个人，他说比第n-2个人大2岁,.....,问第3个人，他说比第2个人大2岁；问第2个人，他说比第1个人大2岁。第1个人说自己10岁，问第n个人多大年纪。

### 编程要求

根据提示，在右侧编辑器补充代码，使用递归法计算游戏人员年龄并输出。

### 测试说明

平台会对你编写的代码进行测试：

测试输入：`5`
预期输出：
`18`

测试输入：`10`；
预期输出：
`28`

### 代码样例

```cpp
#include<iostream>

using namespace std;

int f(int n)
{
    // write your code here
    // make sure that the implementation is by **recursion**
    return n==1?10:(f(n-1)+2);
}
int main()
{
    // write your code here
    int n; cin >> n;
    cout << f(n) << endl;
    return 0;
}
```



## 6.17 任务名称

插入排序的递归实现

### 任务描述

本关任务：插入排序的递归实现

一个数组有n个元素，假如前面n-1个元素已经排序好了，那么把第n个元素插入到前面n-1个元素中，使得数组有序排列，就是插入排序了。

至于n-1个元素如何已经先排序好，那么我们可以假设前面n-2个元素已经排序好，把第n-1个元素插入到前面n-2个元素中。

依次类推，直到只剩下一个元素，也就是第一个元素。排序完成。
```
void Insert_Sort(int A[],int n)
{
	if(n>0)
	{
		Insert_Sort(A,n-1); //递归实现，将前面n-1个元素排序好
		Insert(A,n); // 把第n个元素插入到前面n-1个元素中
	}
	else   //递归的出口是n=0
	   return ;
}
```

提示：测试样例数组长度范围为1~1000，输入数组限整数。


### 编程要求
先输入数组元素的个数；
再输入数组元素；
输出排序后的数组元素
根据提示，在右侧编辑器补充代码，递归实现插入排序，使之符合要求。

### 测试说明

平台会对你编写的代码进行测试：

测试输入：
`4`
`2 3 1 4`
预期输出：
`1 2 3 4`

### 代码样例

```cpp
#include<iostream>
using namespace std;

void Insert_Sort(int A[], int n)
{
    if (n == 0) return ;
    Insert_Sort(A, n-1);
    for (int i=n-2;i>=0;i--) if (A[i]>A[i+1]) {
        int tmp = A[i];
        A[i] = A[i+1];
        A[i+1] = tmp;
    }
}

int main()
{
    int n, a[1010]; cin >> n;
    for (int i=0;i<n;i++) cin >> a[i];
    Insert_Sort(a, n);
    for (int i=0;i<n;i++) cout << a[i] << ' ';
    return 0;
}

```



## 6.18 任务名称

机器人的路线数量

### 任务描述
如图所示，有一个m行n列的网格。起点坐标为(m,n),终点坐标为(1,1)。有一个机器人从起点出发，每次移动只能 移动到当前方格的**下方方格或右方方格**。请设计函数计算，给定方格的行m列n，机器人可以有几种路线到达终点。

![,](/api/attachments/1226415)
例如，当m = n = 2时，共有两种可能的路线。
![,](/api/attachments/1226427)

### 编程要求

程序输入两个整数m,n，输出 路线数量。

### 测试说明

平台会对你编写的代码进行测试：

测试输入：
`1 1`
预期输出：
`1`

测试输入：
`2 2`
预期输出：
`2`

测试输入：
`5 5`
预期输出：
`70`

### 提示：
可以将原问题转化为两个子问题：
如果在(m, n)向右走，则变成了求解输入为(m,n-1)的子问题，即列数变少1单位。如果向下走，则变成了求解输入为(m-1,n)的子问题，即行数变少1单位。而原问题的答案就是两个子问题答案之和。

注意：此题目测试集可以保证使用递归函数不会超时或栈溢出。

### 代码样例

```cpp
#include <iostream>

using namespace std;

int cal_routines(int m ,int n){
    // write your code here
    return (m==1||n==1)?1:(cal_routines(m,n-1) + cal_routines(m-1,n));
}
// NEVER EDIT THE MAIN FUNCTION
int main()
{
    int m, n;
    cin >> m >> n;
    cout << cal_routines(m, n) << endl;
}
```

