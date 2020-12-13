# 实训作业参考答案 —— 第五章 数组（上、下）



## 5.1.1 任务名称

数组排序

### 任务描述


本关任务：输入一个正整数 n，然后再输入 n 个整数，将它们从大到小排序后输出。

程序运行示例：
输入: 5 88 55 77 44 99
输出: 99 88 77 55 44

### 测试说明

测试用例 1：

输入: 5 88 55 77 44 99
输出: 99 88 77 55 44

### 代码样例

```cpp
#include <iostream>
#include <algorithm>
using namespace std;

int main()
{
    int n, a[1010];
    cin >> n;
    for (int i=1;i<=n;i++) cin >> a[i];
    for (int i=1;i<=n;i++) {
        for (int j=1;j<=n-i;j++) if (a[j]<a[j+1]) {
            int tmp = a[j];
            a[j] = a[j+1];
            a[j+1] = tmp;
        }
    }
    for (int i=1;i<=n;i++) cout << a[i] << " \n"[i==n];
    return 0;
}
```





## 5.1.2 任务名称

开灯问题

### 任务描述


本关任务：有 n 盏灯，编号为 1~n。第 1 个人把所有灯打开，第 2 个人按下所有编号为 2 的倍数的开关（这些灯将被关掉），第 3 个人按下所有编号为 3 的倍数的开关（其中关掉的灯将被打开，开着的灯将被关闭），依次类推。一共有 k 个人，问最后有哪些灯开着？编写一个程序，输入 n 和 k，输出开着的灯的编号（k≤n≤1000）。

程序运行示例：
输入：7 3
输出：1 5 6 7


### 测试说明


测试输入 1：

输入：8 4
输出：1 4 5 6 7 8

### 代码样例

```cpp
#include <iostream>
using namespace std;

int main(void) {
    /** Begin **/
    int n, k, lamp[1010];
    cin >> n >> k;
    for (int i=1;i<=n;i++) lamp[i] = 0;
    for (int i=1;i<=k;i++) {
        for (int j=i;j<=n;j+=i) lamp[j] = !lamp[j];
    }
    for (int i=1;i<=n;i++) if (lamp[i])
        cout << i << " ";
    /**  End  **/
    return 0;
}
```





## 5.1.3 任务名称

黑色星期五

### 任务描述


本关任务：黑色星期五是指某天既是 13 号又是星期五。13 号在星期五比在其他日子少吗？为了回答这个问题，编写一个程序，计算每个月的 13 号落在周一到周日的次数。给出 n 年的一个周期，要求计算从 1900 年 1 月 1 日至 1900+n-1 年 12 月 31 日中 13 号落在周一到周日的次数，n 为正整数且不大于 400。（已知 1900 年 1 月 1 日是星期一）。

程序运行示例：
输入：20
输出：34 33 35 35 34 36 33

### 测试说明

测试用例1:
输入：80
输出：137 138 137 138 137 138 135

### 代码样例

```cpp
#include <iostream>
#include <iomanip>
using namespace std;

int main(void) {
    int y=1900, m=1, d=1;
    int yy, mm = 12, dd = 31;
    cin >> yy;
    yy = 1900 + yy - 1;

    int w[7] = {0,0,0,0,0,0,0};
    int M[13] = {0,31,28,31,30,31,30,31,31,30,31,30,31};
    for (int i=0;;i=(i+1)%7) {
        if (d == 13) w[i]++;
        if (y == yy && m == mm && d == dd) break;
        d++;
        if (d > M[m] + (m==2 && ((y%4==0&&y%100!=0)||(y%400==0))))
            m++, d=1;
        if (m > 12) y++, m=1;
    }
    for (int i=0;i<7;i++) cout << w[i] << " ";
    return 0;
}
```





## 5.1.4 任务名称

删除重复数据（双数组版）

### 任务描述


本关任务：编写一个能删除数组中重复数据的程序。


### 编程要求

根据提示，在右侧编辑器补充代码，输入一组数据，“利用一个新的数组”保存其中唯一的元素出现，输出数组中元素个数（假设为n个）并按照原顺序输出所有数字的首次出现。

注意：
（1）引入第二个数组；
（2）输出数组中元素时，不再进行新的判断，只能用`for(int k=0; k<n; k++) cout<<arr[k]`形式；
（3）如果需要读入所有输入的整数，可以采用`while(cin>>x)`这种形式。其表示循环读入数据，并将其放入变量x中。当cin读不到新的数据时候，循环终止。在本地运行时候，可以通过`ctrl+z`结束输入，此时`cin>>x`结果为false。

### 测试说明

平台会对你编写的代码进行测试：

测试输入：`1 2 3 1 2 3`；
预期输出：
`1 2 3`

### 代码样例

```cpp
#include <iostream>
using namespace std;

int main(void) {
    int vis[1010] = {0}, arr[1010];
    int n = 0;
    for (int x; cin >> x;) if (vis[x]++==0) arr[n++] = x;
    for (int k=0; k<n; k++) cout << arr[k] << " ";
    return 0;
}
```



## 5.1.5 任务名称

删除重复数据（单数组版）

### 任务描述


本关任务：编写一个能删除数组中重复数据的程序。


### 编程要求

根据提示，在右侧编辑器补充代码，输入一组数据，删除掉其中的重复数据，输出数组中元素个数（假设为n个）并按照原顺序输出所有数字的首次出现。

注意：不引入第二个数组；输出数组中元素时，不再进行新的判断，只能用`for(int k=0; k<n; k++) cout<<arr[k]`形式

### 测试说明

平台会对你编写的代码进行测试：

测试输入：`1 2 3 1 2 3`；
预期输出：
`1 2 3`

### 代码样例

```cpp
#include <iostream>
using namespace std;

int main(void) {
    /** Begin **/
    int n = 0, arr[101];
    for (; cin>>arr[n]; n++) {
        for (int j=0;j<n;j++) if (arr[j] == arr[n]) {
            n--;
            break;
        }
    }
    for (int k=0; k<n; k++) cout << arr[k] << " ";

    /**  End  **/
    return 0;
}
```





## 5.1.6 任务名称

回文数

### 任务描述


本关任务：回文数是指从左向右念和从右向左念都一样的数。如 12321 就是一个典型的回文数。给定一个进制 B（2≤B≤20，由十进制表示），求出所有的大于等于 1 小于等于 200（十进制下）且它的平方用 B 进制表示是回文数的数。用“A”，“B”，“C”…表示 10，11，12 等等。

编写一个程序，输入整数 B（B 由十进制表示），输出分成多行，每行输出两个 B 进制的数字，第二个数是第一个数的平方，且第二个数是回文数。

程序运行示例：

输入：8
输出：
```
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
```

### 代码样例

```cpp
#include <iostream>
using namespace std;

int main(void) {
    /** Begin **/
    int B;
    cin >> B;
    for (int i=1;i<=200;i++) {
        int arr[25] = {0}, arr2[25] = {0}, is_palin = 1;
        for (int _i=i*i;_i;_i/=B) arr[++arr[0]] = _i%B;
        for (int i=1, j=arr[0]; i<j; i++, j--)
            if (arr[i] != arr[j]) is_palin = 0;
        if (is_palin) {
            for (int _i=i;_i;_i/=B) arr2[++arr2[0]] = _i%B;
            for (int j=arr2[0];j>=1;j--) {
                char tmp = arr2[j]<10?arr2[j]+'0':arr2[j]-10+'A';
                cout << tmp;
            }
            cout << " ";
            for (int j=arr[0];j>=1;j--) {
                char tmp = arr[j]<10?arr[j]+'0':arr[j]-10+'A';
                cout << tmp;
            }
            cout << "\n";
        }
    }
    /**  End  **/
    return 0;
}
```





## 5.1.7 任务名称

改错题-二维数组

### 任务描述


本关任务：输入两个正整数 m 和 n（m，n≤10），然后输入该 m 行 n 列矩阵 mat 中的元素，将该矩阵中的第 1 行移到第 2 行，第 2 行移到第 3 行，······，第 m 行移到第 1 行，最后按照矩阵形式输出数组。

错误代码的运行示例：
输入：
```
3 2
1 2
3 4
5 6
```
输出：
```
5	6	
3	4	
3	4	
```

### 测试说明

测试输入：
```
3 2
1 2
3 4
5 6
```
预期输出：
```
5	6	
1	2	
3	4	
````

输入描述：第一行的两个元素为矩阵的行与列，后面的元素为该矩阵的元素；
输出描述：输出移动后的矩阵元素，矩阵每个元素后跟一个 \t 用于分隔例如：5\t6\t（这里为了方便观察，用 \t 显示）。

### 代码样例

```cpp
// 请在下方添加代码
/********** Begin *********/
#include <iostream>
using namespace std;
const int MAX_SIZE = 10;
int main(){
    int i, j, m, n;
    int mat[MAX_SIZE+1][MAX_SIZE];

    cin>>m>>n;
    for(i = 0; i<m; i++){
        for(j = 0; j<n; j++){
            cin>>mat[i][j];
        }
    }

    for(j = 0; j<n; j++){
        cout<<mat[m-1][j]<<'\t';
    }

    cout<<endl;

    for(i = 0; i<m-1; i++){
        for(j = 0; j<n; j++){
            cout<<mat[i][j]<<'\t';
        }
        cout<<endl;
    }
    
    

    return 0;
}
/********** End **********/

```



## 5.1.8 任务名称

数字金字塔-二维数组

### 任务描述


本关任务：观察下面的数字金字塔，寻找一个算法查找从最高点到底部任意处结束的路径，使路径经过的数字的和最大。每一步可以走到左下方的点也可以到达右下方的点。
```
    7
   3 8
  8 1 1
 2 7 4 4
4 5 2 6 5
```


在上面的例子中，从 7 到 3 到 8 到 7 到 5 的路径产生了最大的数字和。

编写一个程序，首先输入数字金字塔层次数R（1≤R≤10），接着后面的每行为这个数字金字塔特定层包含的整数（所有整数大于等于0且小于100），输出计算出来的最大的和。


> 提示：设置一个两维数组 f，f[i，j] 表示从最高点（最高点为第 1 层）到达第 i 层第 j 个位置时经过路径数字的最大和，则 f[i+1，j]+=Max{ f[i，j-1]，f[i，j]}（1≤i≤r-1，1≤j≤i）。请注意边界值的处理，f[i，0]=0。


程序运行示例：
输入：
```
5
7
3 8
8 1 1
2 7 4 4
4 5 2 6 5
```
输出：30

### 代码样例

```cpp
#include <iostream>
using namespace std;

int f[11][11];

int main(void) {
    /** Begin **/
    int r;
    cin >> r;
    int mx = 0;
    for (int i=1;i<=r;i++) {
        for (int j=1;j<=i;j++) {
            cin >> f[i][j];
            if (f[i-1][j]>f[i-1][j-1])
                f[i][j] += f[i-1][j];
            else
                f[i][j] += f[i-1][j-1];

            if (f[i][j] > mx) mx = f[i][j];
        }
    }
    cout << mx << endl;
    /**  End  **/
    return 0;
}
```



## 5.1.9 任务名称

寻找鞍点-二维数组

### 任务描述


本关任务：在矩阵中，一个元素在所在行中是最大值，在所在列中是最小值，则被称为鞍点（Saddle point）。输入两个正整数 m 和 n（m，n≤10），然后输入该 m 行 n 列矩阵 mat 中的元素，如果找到 mat 的鞍点，就输出它的下标；如果找到多个鞍点，则分行输出它们的下标（行下标小的鞍点优先输出）；否则，输出“Not Found”。

程序运行示例一：
输入:
```
3 4
3 2 1 4
5 1 6 8
6 7 8 9
```
输出：mat[0][3]=4

程序运行示例二：
输入:
```
3 4
3 2 1 9
4 7 6 8
5 1 8 3
```
输出：Not Found

### 代码样例

```cpp
#include<iostream>
using namespace std;

int mat[20][20];
int m=0,n=0;

int pd(int i,int j){
    for(int tj=0;tj<n;tj++){
        if(mat[i][j]<mat[i][tj]){
            return 2;
        }
    }
    for(int ti=0;ti<m;ti++){
        if(mat[i][j]>mat[ti][j]){
            return 2;
        }
    }
    return 1;
}

int main()
{
    cin>>m>>n;
    for(int i=0;i<m;i++){
        for(int j=0;j<n;j++){
            cin>>mat[i][j];
        }
    }
    int p=0;
    for(int i=0;i<m;i++){
        for(int j=0;j<n;j++){
            if(pd(i,j)==1){
                cout<<"mat["<<i<<"]["<<j<<"]="<<mat[i][j]<<endl;
                p=1;
            }
        }
    }
    if(p==0) cout<<"Not Found"<<endl;
    return 0;
}
/********** End **********/
```



## 5.2.1 任务名称

改错题

### 任务描述


本关任务：输入一个字符串（少于80个字符），把字符串中所有的数字字符转换为整数，去掉其他字符。


### 编程要求

在右侧编辑器修改代码，将字符串中所有的数字字符转换为整数并去掉其他字符。

### 测试说明

平台会对你编写的代码进行测试：

测试输入：`pro56gr am93 m4in g`
预期输出：`56934`

### 代码样例

```cpp
#include <iostream>
using namespace std;

int main(){
    int i, j, n = 0;
    char str[80];

    i = 0;
    while((str[i]=cin.get())!='\n')
        i++;
    str[i] = '\0';

    for(j = 0; str[j]!='\0'; j++){
        if(str[j]>='0' && str[j]<='9')
            n = n*10 + str[j]-'0';
    }
    cout << n << endl;
    return 0;
}
```





## 5.2.2 任务名称

统计元音字母个数

### 任务描述


本关任务：输入一个字符串（少于80个字符），统计并输出其中元音字母（AEIOUaeiou）的个数（不区分大小写）。


### 编程要求

在右侧编辑器补充代码，输出字符串中元音字母的个数。

### 测试说明

平台会对你编写的代码进行测试：

测试输入：`I have an apple`
预期输出：`Count=6`

### 代码样例

```cpp
#include <iostream>
using namespace std;

int main() {
    char str[90], t[12]="AEIOUaeiou";
    cin.getline(str, 80);
    int cnt = 0;
    for (int i=0;str[i];i++) {
        for (int j=0;j<10;j++) if (str[i]==t[j]) { cnt++; break; }
    }
    cout << "Count=" << cnt << endl;
    return 0;
}
```





## 5.2.3 任务名称

查找字符

### 任务描述


本关任务：编写一个程序，首先输入一个以回车键结束的字符串（少于80个字符），接着再输入一个字符，查找该字符在字符串中是否存在。如果找到，则输出该字符串在字符串中所对应的**最大下标**（下标从0开始）；否则输出“Not Found”。

可参考如下两个案例便于理解：

案例一输入：
```
program design
g
```
案例一输出：`Index=12`

案例二输入：
```
program design
k
```
案例二输出：`Not Found`



### 编程要求

在右侧编辑器补充代码，判断指定字符是否在字符串中存在，存在输出其**最大下标**，不存在则输出“Not Found”。

### 测试说明

平台会对你编写的代码进行测试：

测试输入：
```
Hello, world!
l
```
预期输出：`Index=10`

### 代码样例

```cpp
#include <iostream>
#include <cstring>
using namespace std;

int main(){
    char s[100], t;
    cin.getline(s, 81); cin.get(t);

    bool f=0;
    for (int i=strlen(s)-1;i>=0;i--) if (s[i]==t) {
        cout << "Index=" << i << endl;
        f=1; break;
    }
    if (!f) cout << "Not Found" << endl;
    return 0;
}
```





## 5.2.4 任务名称

字符重排序

### 任务描述


本关任务：输入一个字符串（少于80个字符），去掉重复的字符后，按照字符的ASCII码值**从大到小**输出。


### 编程要求

在右侧编辑器补充代码，去掉重复字符后按照字符的ASCII码**从大到小**输出。

### 测试说明

平台会对你编写的代码进行测试：

测试输入：`ya7bb2tizx4m55n9q2`
预期输出：`zyxtqnmiba97542`

### 代码样例

```cpp
#include <iostream>
using namespace std;

int main()
{
    char str[81];
    cin.getline(str, 80);
    for (int i=0;str[i];i++) {
        for (int j=i+1;str[j];j++) {
            if (str[i]<str[j]) {
                str[i]^=str[j]^=str[i]^=str[j];
            }
        }
    }
    for (int i=0;str[i];i++) {
        if (i==0 || str[i]!=str[i-1]) cout << str[i];
    }

    return 0;
}
```



## 5.2.5 任务名称

字符数统计

### 任务描述


本关任务：编写一个程序，从键盘上输入一篇英文文章。首先输入英文文章的行数n（1≤n≤10），接着依次输入n行内容（每行少于80个字符）。要求统计出其中的英文字母（不区分大小写）、数字和其他非空白字符的个数。


具体可参考如下案例：

案例输入：
```
2
21st century is the century of technology.
Nowadays, technology is everywhere around us.
```
案例输出：
```
英文字母：71
数字：2
其他字符：3
```

### 编程要求

在右侧编辑器补充代码，统计输入的英文文章中英文字母（不区分大小写）、数字和其他非空白字符的个数。

### 测试说明

平台会对你编写的代码进行测试：

测试输入：
```
6
We focus on essay generation, which is a challenging
task that generates a paragraph-level text
with multiple topics. Progress towards understanding
different topics and expressing diversity in this
task requires more powerful generators and richer
training and evaluation resources.
```
预期输出：
```
英文字母：241
数字：0
其他字符：4
```

### 代码样例

```cpp
#include <iostream>
#include <cstring>
using namespace std;

int main()
{
    int n;
    cin>>n;
    getchar();
    int num = 0;
    int alpha = 0;
    int blank = 0;
    int ascll = 0;
    for (int i=0;i<n;i++){
        char str[80];
        scanf("%[^\n]",&str);
        getchar();
        for (int j=0;j<strlen(str);j++){
            if(str[j]>='0' && str[j]<='9'){
                num+=1;
			      }else if ((str[j]>='a' && str[j]<='z')
                         || (str[j]>='A' && str[j]<='Z')){
                alpha+=1;
            }else {
                ascll+=1;
            }
			      if (str[j]==' ') blank+=1;
        }
    }
    cout<<"英文字母："<<alpha<<endl<<"数字："<<num<<endl<<"其他字符："<<ascll-blank;
    return 0;
}
```





## 5.2.6 任务名称

寻找字符串

### 任务描述


本关任务：输入两个字符串str1和str2，每个字符串是一行，查找str2在str1里首次出现的位置。

### 编程要求

在右侧编辑器补充代码，根据读入的两个字符串，实现查找功能。如果str2在str1中不存在，则输出-1。

注意：（1）每一行不超过160个字符，可以包含任意字符；（2）不使用字符串比较的库函数。

### 测试说明

平台会对你编写的代码进行测试：

测试输入：
```
To be, or not to be:that is the question,
To
```
预期输出：
```
0
```

测试输入：
```
To be, or not to be:that is the question,
Be
```
预期输出：
```
-1
```

### 代码样例

```cpp
#include <iostream>
using namespace std;

int main()
{
    char str1[165], str2[165];
    cin.getline(str1, 161);
    cin.getline(str2, 161);

    bool is_exist = false;
    for (int i=0, j; str1[i]; i++) {
        for (j=0; str2[j]; j++)
            if (str1[i+j] != str2[j]) break;
        if (!str2[j]) {
            cout << i;
            is_exist = true;
            break;
        }
    }
    if (!is_exist) cout << -1;
    return 0;
}
```





## 5.2.7 任务名称

查找回文字符串

### 任务描述


本关任务：编写一个程序，寻找一篇英文文章中**最长**的回文字符串。


**回文字符串**是具有回文特性的字符串：即该字符串从左向右读，与从右向左读都一样。

**输入**文件不会超过10000字符。这个文件可能一行或多行，但是每行都不超过80个字符（不包括最后的换行符）。在寻找回文时只考虑字母 'A' - 'Z' 和 'a' - 'z' ，忽略其他字符（例如：标点符号，空格等）。

**输出**的第一行应该包括找到的最长的回文的**长度**。下一行或几行应该包括这个**回文的原文**（没有除去标点符号，空格等），把这个回文输出到一行或多行（如果回文中包括换行符）。如果有多个回文长度都等于最大值，输出最前面出现的那一个。


### 编程要求

在右侧编辑器补充代码，找出一篇英文文章中最长的回文字符串。

### 测试说明

平台会对你编写的代码进行测试：

测试输入：`Confucius say: Madam, I'm Adam.`
预期输出：
```
11
Madam, I'm Adam
```

### 代码样例

```cpp
#include <iostream>
#include <cstring>
using namespace std;

int main()
{
    char str[500];
    char str_alpha[500];
    int str_index[500];
    int t=0;
    for (;(str[t++]=cin.get())!=-1;) ; str[t]=0;
    int flag = 0;
    for (int i=0;i<strlen(str);i++){
        if ((str[i]>='a' && str[i]<='z') || (str[i]>='A' && str[i]<='Z')){
            char tmp = str[i];
            if (str[i]>='A' && str[i]<='Z'){
                tmp = tmp-'A'+'a';
            }
            str_alpha[flag] = tmp;
            str_index[flag] = i;
            flag+=1;
        }
    }


    int n = flag;
    bool dp[n][n];
    for (int i=0;i<n;i++){
        for (int j=0;j<n;j++){
            dp[i][j] = false;
        }
    }

    int res[2] = {-1,-1};

    for (int i=0;i<n;i++){
        for (int j=i;j>=0;j--){
            if (str_alpha[i] == str_alpha[j] && ((i-j<2) || dp[j+1][i-1])){
                dp[j][i] = true;
                if (res[0] == -1 || ((i-j+1)>(res[1]-res[0]))){
                    res[0] = j;
                    res[1] = i+1;
                }
            }
        }
    }
    cout<<res[1]-res[0]<<endl;
    for (int i=str_index[res[0]];i<=str_index[res[1]-1];i++){
        cout<<str[i];
    }

    return 0;
}
```



## 5.2.8 任务名称

摩尔斯电码

### 任务描述

本关任务：编写一个程序，读入一个英语短语，然后把它编码成摩尔斯码。每个摩尔斯编码字母之间用一个空格，每个摩尔斯编码单词之间用三个空格。


摩尔斯电码（又译为摩斯密码，Morse code）是一种时通时断的信号代码，用一系列圆点和破折号表示字母表中的每个英文字母，每个数字和一些特殊标点符号，如下图1所示。

<p align="center"><img  style="border: 2px solid #ddd;padding: 5px; background: #fff;" src="/api/attachments/1217133" alt=""  height="90%" width="90%" /></p>
<center>图1</center>


### 编程要求

在右侧编辑器补充代码，将英语短语编码成摩尔斯码。

### 测试说明

平台会对你编写的代码进行测试：

测试输入：`SOS`
预期输出：`... --- ...`

### 代码样例

```cpp
#include <iostream>
#include <cstring>

using namespace std;

char alp[30][8] = {
    ".-", "-...", "-.-.", "-..",
    ".", "..-.", "--.", "....",
    "..", ".---", "-.-", ".-..",
    "--", "-.", "---", ".--.",
    "--.-", ".-.", "...", "-",
    "..-", "...-", ".--", "-..-",
    "-.--", "--.."
};
char num[15][8] = {
    "-----", ".----", "..---", "...--",
    "....-", ".....", "-....", "--...",
    "---..", "----."
};
int main()
{
    char s[101];
    cin.getline(s, 100);
    for (int i=0;s[i];i++) {
        if ('a' <= s[i] && s[i] <= 'z') cout << alp[s[i]-'a'] << " ";
        else if ('A' <= s[i] && s[i] <= 'Z') cout << alp[s[i]-'A'] << " ";
        else if ('0' <= s[i] && s[i] <= '9') cout << num[s[i]-'A'] << " ";
        else cout << s[i] << " ";
    }
    return 0;
}
```

