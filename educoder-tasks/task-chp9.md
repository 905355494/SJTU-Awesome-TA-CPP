# 实训作业参考答案 —— 第九章 模块化开发



## 9.1.1 股票分析系统

## 题目描述

设计一个股票价格分析程序，实现对一支股票价格和买卖策略的分析。它具有如下功能：

命令 **1** ：开始输入股票价格序列，以空格分隔，-1结束输入。它的第 *i* 个元素是一支给定股票第 *i* 天的价格。若之前存在序列，则将先前序列清空后更新为当前输入序列。

命令 **2** ：查询股票价格。将当前股票的价格序列输出在屏幕上。

命令 **3** ：将股票价格序列按升序排序后输出在屏幕上。

命令 **4**：输出出现股票价格最大值和最小值的日期。

命令 **5** ：如果你最多只允许完成一笔交易（即买入和卖出一支股票一次），输出你所能获取的最大利润。注意：你不能在买入股票前卖出股票。如，当前的股票价格序列为[7,1,5,3,6,4]，则输出结果为5。具体买卖方式为：在第 2 天（股票价格 = 1）的时候买入，在第 5 天（股票价格 = 6）的时候卖出，最大利润 = 6-1 = 5 。注意利润不能是 7-1 = 6, 因为卖出价格需要大于买入价格；同时，你不能在买入前卖出股票。

命令 **6** ：如果你可以尽可能地完成更多的交易（多次买卖该股票），输出你所能获得的最大利润。注意：你不能同时参与多笔交易（你必须在再次购买前出售掉之前的股票）。如，当前股票价格序列为[7,1,5,3,6,4]，则输出结果为7。具体买卖方式为：在第 2 天（股票价格 = 1）的时候买入，在第 3 天（股票价格 = 5）的时候卖出, 这笔交易所能获得利润 = 5-1 = 4 。随后，在第 4 天（股票价格 = 3）的时候买入，在第 5 天（股票价格 = 6）的时候卖出, 这笔交易所能获得利润 = 6-3 = 3 。

命令 **7** ：退出

程序运行时，出现菜单：

```
欢迎使用股票分析系统：
1 -- 输入股票价格序列
2 -- 查询股票价格
3 -- 输出升序的股票价格序列
4 -- 输出最大值和最小值日期
5 -- 一笔交易的最大利润
6 -- 多笔交易的最大利润
```
## 任务说明
你的任务是自行设计函数，并且在main函数中调用自己设计的函数，完成题目的要求。


## 测试样例

样例1：
输入：
```
1
7 1 5 3 6 4 -1
2
3
4
5
6
7
```
输出：
```
欢迎使用股票分析系统：
1--输入股票价格序列
2--查询股票价格
3--输出升序的股票价格序列
4--输出最大值和最小值的日期
5--一笔交易的最大利润
6--多笔交易的最大利润
7--退出
7 1 5 3 6 4 
1 3 4 5 6 7 
1 0
5
7
```

样例2：
输入：
```
1
1 2 3 4 5 -1
2
3
4
5
6
7
```
输出：
```
欢迎使用股票分析系统：
1--输入股票价格序列
2--查询股票价格
3--输出升序的股票价格序列
4--输出最大值和最小值的日期
5--一笔交易的最大利润
6--多笔交易的最大利润
7--退出
1 2 3 4 5 
1 2 3 4 5 
0 4
4
4
```

样例3:
输入：
```
1
7 6 5 4 3 2 1 -1
2
3
4
5
6
7
```
输出：
```
欢迎使用股票分析系统：
1--输入股票价格序列
2--查询股票价格
3--输出升序的股票价格序列
4--输出最大值和最小值的日期
5--一笔交易的最大利润
6--多笔交易的最大利润
7--退出
7 6 5 4 3 2 1 
1 2 3 4 5 6 7 
6 0
0
0
```

### 代码样例

```cpp
#include <iostream>
#include <cstdio>

using namespace std;

void showOption(){
    cout<<"欢迎使用股票分析系统："<<endl;
    cout<<"1--输入股票价格序列"<<endl;
    cout<<"2--查询股票价格"<<endl;
    cout<<"3--输出升序的股票价格序列"<<endl;
    cout<<"4--输出最大值和最小值的日期"<<endl;
    cout<<"5--一笔交易的最大利润"<<endl;
    cout<<"6--多笔交易的最大利润"<<endl;
    cout<<"7--退出"<<endl;
}

// Your code here
void input(int p[], int &n){
    int x;
    n=0;
    cin>>x;
    while(x!=-1){
        p[n++]=x;
        cin>>x;
    }
}
void query(int p[], int n){
    for(int i=0;i<n;i++){
        cout<<p[i]<<' ';
    }
    cout<<endl;
}
void sort(int p[], int n){
    int *pt = new int[n];
    for(int i=0;i<n;i++){
        pt[i]=p[i];
    }
    int tmp;
    bool flag=true;
    for(int i=0;i<n-1&&flag;i++){
        flag=false;
        for(int j=0;j<n-1-i;j++){
            if(pt[j]>pt[j+1]){tmp=pt[j];pt[j]=pt[j+1];pt[j+1]=tmp;flag=true;}
        }
    }
    query(pt,n);
    delete [] pt;
}
void maxmin(int p[],int n){
    int max=p[0], min=p[0], dmax=0, dmin=0;
    for(int i=0;i<n;i++){
        if(p[i]>max){dmax=i;max=p[i];}
        if(p[i]<min){dmin=i;min=p[i];}
    }
    cout<<dmin<<' '<<dmax<<endl;
}
void profit1(int p[],int n){
    int pf=0;
    for(int i=1;i<n;i++){
        for(int j=0;j<i;j++){
            if(p[i]-p[j]>pf)pf=p[i]-p[j];
        }
    }
    cout<<pf<<endl;
}
void profit2(int p[],int n){
    int pf=0;
    for(int i=1;i<n;i++){
        if(p[i-1]<p[i])pf+=p[i]-p[i-1];
    }
    cout<<pf<<endl;
}

int main()
{
    int x,n=0,p[100];
    bool flag=true;
    showOption();
    while(flag){
        cin>>x;
        switch(x){
            case 1: input(p,n); break;
            case 2: query(p,n); break;
            case 3: sort(p,n); break;
            case 4: maxmin(p,n); break;
            case 5: profit1(p,n); break;
            case 6: profit2(p,n); break;
            case 7: flag=false;
        }
    }
    // Your code here
    return 0;
}
```



## 9.2.1 绘制龟图

## 题目描述

Logo语言在个人计算机用户计算中非常流行，该语言形成了龟图的概念。假设有个机器海龟，通过C++控制在房子中移。在两个方向之一打开画笔，即向上或向下。
画笔向下时，海龟跟踪移动的形状并留下移动的路径；画笔向上时，海龟自由移动，不写下任何东西。在这个问题中，要模拟海龟的操作和生成计算机化的草图框。
用20X20数组floor，初始化为0。跟踪任何时候海龟当前的位置和画笔的向上或向下状态。假设海龟总是从位置0，0开始，画笔向上。程序要处理的海龟命令如下：

| 命令 |         含义         |
| :--: | :------------------: |
|  1   |        笔向上        |
|  2   |        笔向下        |
|  3   |         左转         |
|  4   |         右转         |
| 5 n  | 前进n格（n为正整数） |
|  6   |    打印20*20数组     |
|  9   |   数据结束（标记）   |


当收到向下命令后，画笔仅仅向下，不改变当前位置的值，当画笔向下并移动海龟时，将数组floor的相应元素设置为1（但不影响起始点的值）。指定命令6（打印）时，只要数组元素值为1，就显示星号或其他符号，而数组元素值为0则显示空白。

## 任务要求
你的任务是自行设计函数，并且在main函数中调用自己设计的函数，完成题目的要求。

## 样例
输入
下列程序绘制和打印13X13正方形并让画笔向上。程序刚启动时，笔是向上的。
`2`
`5 12`
`3`
`5 12`
`3`
`5 12`
`3`
`5 12`
`1`
`6`
`9`

输出（注意空格也是输出的一部分）：
`*************       `
`*           *       `
`*           *       `
`*           *       `
`*           *       `
`*           *       `
`*           *       `
`*           *       `
`*           *       `
`*           *       `
`*           *       `
`*           *       `
`*************       `
`                    `
`                    `
`                    `
`                    `
`                    `
`                    `
`                    `

### 代码样例

```cpp
#include <iostream>
#include <cstring>

using namespace std;

void showOption(){
    cout<<"欢迎来到Logo绘制系统："<<endl;
    cout<<"1--笔向上"<<endl;
    cout<<"2--笔向下"<<endl;
    cout<<"3--左转"<<endl;
    cout<<"4--右转"<<endl;
    cout<<"5 n--前进n格（n为正整数）"<<endl;
    cout<<"6--打印20*20数组"<<endl;
    cout<<"9--数据结束（标记）"<<endl;
}

// Your code here
void go(int fl[][20],int d,int n,int &x,int &y){
    switch(d){
        case 0: for(int i=0;i<n;i++){x++;fl[x][y]=1;} break;
        case 1: for(int i=0;i<n;i++){y++;fl[x][y]=1;} break;
        case 2: for(int i=0;i<n;i++){x--;fl[x][y]=1;} break;
        case 3: for(int i=0;i<n;i++){y--;fl[x][y]=1;} break;
    }
}
void print(int fl[][20]){
    for(int i=0;i<20;i++){
        for(int j=0;j<20;j++){
            if(fl[i][j]==0)cout<<' ';
            else cout<<'*';
        }
        cout<<endl;
    }
}

int main()
{
    showOption();
    int inp, floor[20][20]={0}, pan=0, n, x=0, y=0, d=0;
    bool flag=true;
    while(flag){
        cin>>inp;
        switch(inp){
            case 1: pan=0;break;
            case 2: pan=1;d=0;break;
            case 3: pan=2;d=(d+1)%4;break;
            case 4: pan=3;d=(d-1+4)%4;break;
            case 5: cin>>n;go(floor,d,n,x,y);break;
            case 6: print(floor);break;
            case 9: flag=false; break;
        }
    }

    // Your code here

    return 0;
}
```



