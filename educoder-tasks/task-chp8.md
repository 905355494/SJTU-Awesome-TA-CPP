# 实训作业参考答案 —— 第八章 结构体



## 8.1.1 时钟

### 任务描述


模拟一个用于时间的电子时钟。该时钟以时、分和秒的形式记录时间。编写3个函数：
* `setTime` 函数用于设置时钟的时间，
* `increase` 函数模拟时间过去了1秒，
* `showTime` 显示当前时间，显示格式为HH:MM:SS。

**注意时钟为24小时制。**


### 测试说明


输入描述：六个整型，分别代表第一次输入的时、分、秒和第二次输入的时、分、秒。

输出描述： 将输出每次输入的时间以及增加一秒后的时间

样例输入：`12 48 56 13 2 16 `

样例输出：

```cpp
12:48:56
12:48:57
13:02:16
13:02:17
```

### 代码样例

```cpp
#include <iostream>
using namespace std;

struct T{
    int h, m, s;
};

void setTime(T &t){
    cin>>t.h>>t.m>>t.s;
}
void increase(T &t){
    t.s++;
    if(t.s>=60){
        t.s-=60;t.m++;
        if(t.m>=60){
            t.m-=60;t.h++;
            if(t.h>=24){
                t.h-=24;
            }
        }
        }
}
void showTime(const T &t){
    char s[9]="00:00:00";
    s[0]=t.h/10+'0';
    s[1]=t.h%10+'0';
    s[3]=t.m/10+'0';
    s[4]=t.m%10+'0';
    s[6]=t.s/10+'0';
    s[7]=t.s%10+'0';
    cout<<s<<endl;
}
int main()
{
    T t1, t2;
    setTime(t1);
    setTime(t2);
    showTime(t1);
    increase(t1);
    showTime(t1);
    showTime(t2);
    increase(t2);
    showTime(t2);

    return 0;
}
```



## 8.1.2 复数

### 任务描述

用结构体表示一个复数，编写实现复数的加法、乘法、和输出的函数。

* 加法规则：$$(a+bi)+(c+di)=(a+c)+(b+d)i$$
* 乘法规则：$$(a+bi)×(c+di)=(ac-bd)+(bc+ad)i$$
* 输出规则：如果$$a$$是实部，$$b$$是虚部，输出格式为$$a+bi$$


### 测试说明

输入描述：四个整型 $$a$$, $$b$$, $$c$$, $$d$$ ，分别是复数 $$x = a + bi$$ 和 $$y = c + di$$

输出描述：

将依次输出

```
x = ?
y = ?
x += y; x = ?
y *= x; y = ?
x + y = ?
y * x = ?
x = ?
y = ?
```

样例输入1：`1 2 3 4`

样例输出1：

```cpp
x = 1+2i
y = 3+4i
x += y; x = 4+6i   
y *= x; y = -12+34i
x + y = -8+40i     
y * x = -252+64i   
x = 4+6i
y = -12+34i 
```

### 代码样例

```cpp
#include <iostream>
using namespace std;

struct Comp{
    int a,b;
};
void showComp(const Comp &cp){
    if(cp.a==0&&cp.b!=0)cout<<cp.b<<'i'<<endl;
    else if(cp.b>0)
        cout<<cp.a<<'+'<<cp.b<<'i'<<endl;
    else if(cp.b<0)
        cout<<cp.a<<'-'<<-cp.b<<'i'<<endl;
    else
        cout<<cp.a<<endl;
}
void setComp(Comp &cp){
    cin>>cp.a>>cp.b;
}
void add(Comp &r, const Comp &x, const Comp &y){
    r.a=x.a+y.a;
    r.b=x.b+y.b;
}
void mult(Comp &r, const Comp &x, const Comp &y){
    r.a=x.a*y.a-x.b*y.b;
    r.b=x.a*y.b+x.b*y.a;
}
int main()
{
    Comp r,x,y;
    setComp(x);
    setComp(y);
    cout<<"x = ";
    showComp(x);
    cout<<"y = ";
    showComp(y);
    add(r,x,y);
    x=r;
    cout<<"x += y; x = ";
    showComp(x);
    mult(r,x,y);
    y=r;
    cout<<"y *= x; y = ";
    showComp(y);
    add(r,x,y);
    cout<<"x + y = ";
    showComp(r);
    mult(r,x,y);
    cout<<"y * x = ";
    showComp(r);
    cout<<"x = ";
    showComp(x);
    cout<<"y = ";
    showComp(y);

    return 0;
}
```



## 8.1.3 通讯录

### 任务描述


通信录包含
* “姓名”（最多20个字符）、
* “生日”（包括“年”、“月”、“日”）、
* “电话号码”、
* “家庭地址”（最多50个字符）。

定义一个嵌套的结构类型，输入$$n(n<10)$$个学生信息，再按照他们的年龄从小到大的顺序输出。

### 测试说明

样例输入：

```cpp
2 
Wangwu 1990 12 11 13901232222 No. 800 Dongchuan Road
Zhangsan 1993 1 23 18912337789 No.238 Huasan Road
```

样例输出：

```cpp
Zhangsan 1993 1 23 18912337789 No.238 Huasan Road
Wangwu 1990 12 11 13901232222 No. 800 Dongchuan Road
```


### 测例文件
由于 EduCoder 对测例输入没有换行显示，因此提供了测例文件供同学们本地测试。
请点击右上角的小文件夹，进入 `lab_addressbook/cases/` 查看测例文件。

### 代码样例

```cpp
#include <iostream>

using namespace std;
struct Birthday{
    int y,m,d;
};
struct Contacts{
    char name[20];
    Birthday bd;
    char phone[20];
    char address[50];
};
void setCont(Contacts &c){
    cin>>c.name>>c.bd.y>>c.bd.m>>c.bd.d>>c.phone;
    cin.get();
    cin.getline(c.address,50);
}
void showCont(const Contacts &c){
    cout<<c.name<<' '<<c.bd.y<<' '<<c.bd.m<<' '<<c.bd.d<<' '<<c.phone<<' '<<c.address<<endl;
}
bool great(Contacts &c1, Contacts &c2){
    if(c1.bd.y>c2.bd.y)return true;
    else if(c1.bd.y<c2.bd.y)return false;
    else if(c1.bd.m>c2.bd.m)return true;
    else if(c1.bd.m<c2.bd.m)return false;
    else if(c1.bd.d>=c2.bd.d)return true;
    else if(c1.bd.d<c2.bd.d)return false;
}
void sort(Contacts carr[], int n){
    Contacts tmp;
    bool flag=true;
    for(int i=0; i<n-1&&flag; i++){
        flag=false;
        for(int j=0; j<n-i-1; j++){
            if(great(carr[j+1],carr[j])){tmp=carr[j];carr[j]=carr[j+1];carr[j+1]=tmp;flag=true;}
        }
    }
}
int main()
{
    int n;
    cin>>n;
    Contacts *p = new Contacts[n];
    for(int i=0;i<n;i++){
        setCont(p[i]);
    }
    sort(p,n);
    for(int i=0;i<n;i++){
        showCont(p[i]);
    }
    delete []p;
    return 0;
}
```



## 8.2.1 矩阵

### 任务描述

数学上，一个 $$m \times n$$ 的矩阵是一个由 $$m$$ 行（row）$$n$$ 列（column）元素排列成的矩形阵列。矩阵里的元素可以是数字、符号或数学式。以下是一个由6个数字元素构成的2行3列的矩阵：

$$\begin{pmatrix}1 & 9 & -13 \\\\ 20 & 5 & -6 \end{pmatrix}$$

大小相同（行数列数都相同）的矩阵之间可以相互加减，具体是对每个位置上的元素做加减法。

矩阵的乘法则较为复杂。两个矩阵可以相乘，当且仅当第一个矩阵的列数等于第二个矩阵的行数。矩阵的乘法满足结合律和分配律，但不满足交换律。

两个矩阵的乘法仅当第一个矩阵$$\mathbf{A}$$的列数(column)和另一个矩阵$$\mathbf {B}$$ 的行数(row)相等时才能定义。如$$\mathbf{A}$$是$$m\times n$$矩阵和 $$\mathbf {B}$$ 是 $$n \times p$$ 矩阵，它们的乘积$$\mathbf{AB}$$是一个$$m\times p$$矩阵，它的一个元素

$$AB_{i,j}= A_{i,1}B_{1,j} + A_{i,2}B_{2,j} + \cdots + A_{i,n}B_{n,j} = \sum_{r=1}^n A_{i,r}B_{r,j}$$

其中$$1\leq i\leq m,\ 1\leq j\leq p'$$、。

例如
$$\begin{bmatrix} 1 & 0 & 2 \\\\ -1 & 3 & 1 \\\\  \end{bmatrix} \times \begin{bmatrix} 3 & 1 \\\\  2 & 1 \\\\  1 & 0 \end{bmatrix} = \begin{bmatrix} (1 \times 3  +  0 \times 2  +  2 \times 1) & (1 \times 1   +   0 \times 1   +   2 \times 0) \\\\ (-1 \times 3  +  3 \times 2  +  1 \times 1) & (-1 \times 1   +   3 \times 1   +   1 \times 0) \\\\  \end{bmatrix} = \begin{bmatrix} 5 & 1 \\\\ 4 & 2 \\\\ \end{bmatrix}$$

现在请你设计一个 $$2 \times 2$$ 的矩阵结构体，然后计算一个矩阵 $$A$$ 的 $$n$$ 次幂。为了避免整型溢出，请输出矩阵中每个元素模 $$10^9+7$$ 后的结果。

### 测试说明

输入描述：一个整数 $$n$$ 代表幂次；四个整型 $$a, b, c ,d$$ ，分别代表矩阵 $$A$$ 的四个元素。
$$A = \begin{pmatrix}a & b \\\\ c & d \end{pmatrix}$$

输出描述： $$A^n$$ 中每个元素模$$10^9+7$$ 后的结果。

样例1：

```cpp
100 
1 0 
0 1
```

样例输出1：

```cpp
1 0 
0 1
```

解释1：

$$\begin{pmatrix}1 & 0 \\\\ 0 & 1 \end{pmatrix}^{100} = \begin{pmatrix}1 & 0 \\\\ 0 & 1 \end{pmatrix}$$

样例输入2：

```cpp
3 
1 2 
3 4
```

样例输出2：

```cpp
37    54
81   118
```

解释1：

$$\begin{pmatrix}1 & 2 \\\\ 3 & 4 \end{pmatrix}^{3} = \begin{pmatrix}37 & 54 \\\\ 81 & 118 \end{pmatrix}$$

#### 提示

注意$$0\le n \le 10^{9}$$，直接使用循环乘法可能会超时，请观察如下整数的快速幂算法，仿写矩阵的快速幂算法。算法复杂度 $$O(\log n)$$

```cpp
int fpower(int x, int n) {
    // 计算 x^n, 复杂度 O(log n)
    int ans = 1;
    while (n) {
        if (n % 2) ans *= x;
        x *= x;
        n /= 2;
    }
    return ans;
}
```

### 代码样例

```cpp
#include <iostream>
using namespace std;
struct mat{
    unsigned long int a,b,c,d;
};
void setMat(mat &m){
    cin>>m.a>>m.b>>m.c>>m.d;
}
mat mult(const mat &a,const mat &b){
    mat r;
    unsigned long int tmp = 1000000007;
    r.a=(tmp+a.a*b.a+a.b*b.c)%tmp;
    r.b=(tmp+a.a*b.b+a.b*b.d)%tmp;
    r.c=(tmp+a.c*b.a+a.d*b.c)%tmp;
    r.d=(tmp+a.c*b.b+a.d*b.d)%tmp;
    return r;
}
void fpower(mat &r, mat &m, int n){
    r.a=1;r.b=0;r.c=0;r.d=1;
    while(n){
        if(n%2) r=mult(r,m);
        m=mult(m,m);
        n/=2;
    }
}
void prnMat(const mat &m){
    cout<<m.a<<' '<<m.b<<endl;
    cout<<m.c<<' '<<m.d<<endl;
}
int main()
{
    int n;
    mat m,r;
    cin>>n;
    setMat(m);
    fpower(r,m,n);
    prnMat(r);
    return 0;
}
```



## 8.2.2 单链表（改错题）

## 任务描述

本题基于实验指导书p85，实验11。

输入若干个正整数（输入-1作为输入结束标志），要求按照输入顺序的逆序建立一个单链表，并输出。

程序运行示例：
请输入若干个正整数（-1结束）

```
1 4 89 56 -1
```

按照输入顺序逆序输出

```
56 89 4 1
```

## 错误程序
以下代码清单是有错的源程序，请进行改正。

```cpp
#include <iostream>
using namespace std;

struct List
{
    int num;
    List *next;
};

int main()
{
    List *head,*p,*q;
    int num;

    head = NULL;
    cout << "请输入若干个正整数（-1结束）\n";
    cin >> num;
    while(num != -1)
    {
        p = new List;
        p->num = num;
        head = p->next;
        head = p;
        cin >> num;
    }

    cout << "按照输入顺序逆序输出\n";
    for(p = head; p->next != NULL; p = p->next)
    {
        cout << p->num << " ";
    };
    cout << endl;

    for(p = head; p != NULL; p = q)
    {
        q = p->next;
      delete p;
    }

    return 0;
}
```

### 代码样例

```cpp
#include <iostream>
using namespace std;

struct List
{
    int num;
    List *next;
};

int main()
{
    List *head,*p,*q;
    int num;

    head = NULL;
    p = new List;
    p->next = NULL;
    //cout << "请输入若干个正整数（-1结束）\n";
    cin >> num;
    while(num != -1)
    {
        q = new List;
        q->next = p;
        q->num = num;
        p=q;
        head = p;
        cin >> num;
    }

    //cout << "按照输入顺序逆序输出\n";
    for(p = head; p->next != NULL; p = p->next)
    {
        cout << p->num << " ";
    };
    cout << endl;

    for(p = head; p != NULL; p = q)
    {
        q = p->next;
      delete p;
    }

    return 0;
}
```



## 8.2.3 学生成绩管理

### 任务描述

本题改编自实验指导书p95，实验12的第(2)题。

设计一个学生成绩管理程序，实现对n个学生的3门课程的成绩的记录与统计工作。学生信息包括：学号，姓名，课程成绩1，课程成绩2，课程成绩3。
程序基本功能要求如下：

```
1---添加学生信息（依次输入学号、三门课程的分数、姓名）
2---修改学生信息（依次输入学号、三门课程的分数、姓名）
3---按学号删除学生（输入学号）
4---按学号查询学生信息（输入学号，输出学号、姓名、三门课程的分数）
5---按姓名查询学生信息（输入姓名，按学号升序依次输出学生信息）
6---按学号升序排序
7---按总分降序排序
0---退出
```

### 提示
1. 本题不做复杂度要求。
2. 学生数 $$n<1000$$, 姓名字符不超过50，姓名可能带有空格，姓名可能重复，但学号具有唯一性。
3. 按总分降序排序时，同分的学生按照学号升序输出。
4. 注意考虑以下异常输入
   - 操作1 试图添加重复学生：以新添加的学生更新
   - 操作2 试图修改不存在的学生信息：不做任何修改
   - 操作3 试图删除不存在的学生：不做任何修改
   - 操作4 查找不存在的学号：不输出任何信息
   - 操作5 查找不存在的学生姓名：不输出任何信息

### 测试说明

测试将包括若干行，每行的第一个数代表操作，输入0时程序结束。


样例输入：

```cpp
1 520021910437 99 100 98 Zhang San
1 520021910438 99 100 92 Zhang San
1 520021910439 90 100 94 Li Si
1 520021910440 90 100 94 Wang Wu
2 520021910437 89 100 94 Zhang San
3 520021910430
4 520021910437
5 Zhang San
6
7
0
```

样例输出（此处增加了换行以方便解释）：

```cpp
520021910437 Zhang San 89 100 94

520021910437 Zhang San 89 100 94
520021910438 Zhang San 99 100 92

520021910437 Zhang San 89 100 94
520021910438 Zhang San 99 100 92
520021910439 Li Si 90 100 94
520021910440 Wang Wu 90 100 94

520021910438 Zhang San 99 100 92
520021910439 Li Si 90 100 94
520021910440 Wang Wu 90 100 94
520021910437 Zhang San 89 100 94
```

解释

从输入4开始，数据库的信息已经固定为

```
520021910437 Zhang San 89 100 94
520021910438 Zhang San 99 100 92
520021910439 Li Si 90 100 94
520021910440 Wang Wu 90 100 94
```

接下来将分别做
```
4 输出学号为 520021910437 的学生信息
5 输出姓名为 Zhang San 的学生信息
6 按学号升序输出学生信息
7 按总分降序输出学生信息
```

### 提示2

本题代码量较大。因此增加了一层提示。

一种可能的结构体设计。

```cpp
struct Student
{
    long long sid;
    char name[50];
    int grades[3];
};
```

一种可能的输入设计。当然请不必拘泥于这种方式。

```cpp
Student students[1005];
int n_students = 0;

/*
    操作1： 添加学生信息
*/
void insert_student() {
    long long sid; cin >> sid;

    // 检查学生是否已存在
    int pos = 0;
    while (pos < n_students && students[pos].sid != sid) pos++;
    
    Student& s = students[pos]; s.sid = sid;
    for (int i = 0; i < 3; ++i) cin >> s.grades[i];
    cin >> ws; // skip whitespace
    cin.getline(s.name, 50);
    if (pos < n_students) return; // 更新已存在的学生时并不增加学生总数
    n_students++;
}
```

### 测例文件
由于 EduCoder 对测例输入没有换行显示，因此提供了测例文件供同学们本地测试。
请点击右上角的小文件夹，进入 `lab08_学生成绩管理程序/cases/` 查看测例文件。

### 代码样例

```cpp
#include <iostream>
#include <cstring>
using namespace std;
struct Stu{
    char no[20];
    char name[50];
    int score[3];
};
int findStu(char *no, Stu s[], int &n){
    int i;
    for(i=0;i<n;i++){
        if(strcmp(no,s[i].no)==0)break;
    }
    return i;
}
int findStu_name(char *name, Stu s[], const int &n){
    int i;
    for(i=0;i<n;i++){
        if(strcmp(name,s[i].name)==0)break;
    }
    return i;
}
void prnStu(const Stu &s){
    cout<<s.no<<' '<<s.name<<' '<<s.score[0]<<' '<<s.score[1]<<' '<<s.score[2]<<' '<<endl;
}
void inputStu(Stu s[], int &n){
    char no[20];
    cin>>no;
    int i =findStu(no,s,n);
    strcpy(s[i].no,no);
    cin>>s[i].score[0]>>s[i].score[1]>>s[i].score[2];
    cin.get();
    cin.getline(s[i].name,50);
    if(i==n)n++;
}
void changeStu(Stu s[], int &n){
    char no[20];
    cin>>no;
    int i =findStu(no,s,n);
    cin>>s[i].score[0]>>s[i].score[1]>>s[i].score[2];
    cin.get();
    cin.getline(s[i].name,50);
}
void deleteStu(Stu s[], int &n){
    char no[20];
    cin>>no;
    cin.get();
    int i =findStu(no,s,n);
    if(i<n){
        for(int j=i;j<n-1;j++){
            s[j]=s[j+1];
        }
        n--;
    }
}
void queryStu(Stu s[], int &n){
    char no[20];
    cin>>no;
    cin.get();
    int i =findStu(no,s,n);
    if(i<n){
        prnStu(s[i]);
    }
}
void sort_no(Stu s[], int &n){
    Stu tmp;
    bool flag=true;
    for(int i=0;i<n-1&&flag;i++){
        flag=false;
        for(int j=0;j<n-i-1;j++){
            if(strcmp(s[j].no,s[j+1].no)>0){tmp=s[j];s[j]=s[j+1];s[j+1]=tmp;flag=true;}
        }
    }
    for(int i=0;i<n;i++){
        prnStu(s[i]);
    }
}
void queryStu_name(Stu s[], int &n){
    char name[50];
    int k=0, narr[100], i=0;
    cin.getline(name,50);
    while(i<n){
        i +=findStu_name(name,s+i,n-i);
        if(i<n)narr[k++]=i++;
    }
    if(k!=0){
        Stu *sp=new Stu[k];
        for(int j=0;j<k;j++){
            sp[j]=s[narr[j]];
        }
        sort_no(sp,k);
    } 
}
int totalscore(const Stu &s){
    return s.score[0]+s.score[1]+s.score[2];
}
void sort_score(Stu s[], int &n){
    int *score=new int[n];
    int *id=new int[n];
    for(int i=0;i<n;i++){
        id[i]=i;
        score[i]=totalscore(s[i]);
    }

    int tmp;
    bool flag=true;
    for(int i=0;i<n-1&&flag;i++){
        flag=false;
        for(int j=0;j<n-i-1;j++){
            if(score[j]==score[j+1]){
                if(strcmp(s[j].no,s[j+1].no)>0){tmp=id[j];id[j]=id[j+1];id[j+1]=tmp;flag=true;}
                }
            if(score[j]<score[j+1]){tmp=score[j];score[j]=score[j+1];score[j+1]=tmp;
            tmp=id[j];id[j]=id[j+1];id[j+1]=tmp;flag=true;}
        }
    }
    for(int i=0;i<n;i++){
        prnStu(s[id[i]]);
    }
}	
int main()
{
    Stu s[1000];
    int n=0,x;
    bool flag = true;
    while(flag){
        cin>>x;
        cin.get();
        switch(x){
            case 1: inputStu(s,n); break;
            case 2: changeStu(s,n); break;
            case 3: deleteStu(s,n); break;
            case 4: queryStu(s,n); break;
            case 5: queryStu_name(s,n); break;
            case 6: sort_no(s,n); break;
            case 7: sort_score(s,n); break;
            case 0: flag=false; break;
        }
    }
    return 0;
}
```





## 8.3.1 反转链表

### 任务描述

反转一个单链表。

### 编程要求

**你只需要正确地实现反转链表的函数 `reverseList` 。**

```cpp
ListNode* reverseList(ListNode* head) {
    ...
}
```

`reverseList` 函数接受一个链表的头指针作为参数，返回一个链表指针。返回的链表与传入的链表刚好是逆序的。

`main` 函数我们已经帮你写好。它的功能是将输入的一串数字构造为单链表，然后测试你书写的 `reverseList` 函数。

本地测试时，请用 `Ctrl Z`（Windows 下） 结束 `cin >> x` 的输入。对于 类 Unix 的系统，请使用 `Ctrl D`。

### 测试说明

示例1:

输入: 
```
1 2 3 4 5
```

输出: 
```
1->2->3->4->5->nullptr
5->4->3->2->1->nullptr
```

示例2:

输入: 

```

```

输出: 
```
nullptr
nullptr
```

### 代码样例(By 李瑞)

```cpp
#include <iostream>
using namespace std;

struct ListNode {
    int val;
    ListNode *next;
};
ListNode* reverseList(ListNode* head) {
    /********* Begin *************/
ListNode *prev = nullptr;
	ListNode *curr = head;
	while (curr != nullptr)
	{
		ListNode *next = curr->next;
		curr->next = prev;
		prev = curr;
		curr = next;
	}
	return prev;
    /********* End *************/
}
ListNode* createList() {
    int x;
    ListNode head; 
    ListNode* p = &head; head.next = NULL;
    while (cin >> x) {
        p->next = new ListNode; p->next->val = x; p->next->next = NULL;
        p = p->next; 
    }
    return head.next;
}
void displayList(ListNode* p) {
    while (p)
    {
        cout<<p->val<<" -> ";
        p = p->next;
    }
    cout<<"nullptr\n";
}
int main()
{
    ListNode* L1 = createList(); displayList(L1);
    ListNode* L2 = reverseList(L1); displayList(L2);
    return 0;
}
```



## 8.3.2 多项式加法

### 任务描述


本关任务：编写一个能利用链表实现整系数多项式加法的程序。


### 编程要求

根据提示，在右侧编辑器补充代码，利用链表实现整系数多项式的加法Node* add_poly(Node* a, Node* b)。多项式a和b用链表表示，链表定义如下：

struct Node {
  int order, coeff; // 次数 和 系数
  Node* nxt; // 指向后一项的指针
}


多项式a和b保证每一项系数coeff都是整数，保证每一项次数order >= 0。输入order=-1表示输入结束。保证从链表的头到尾，次数递减，详见 sample case。


结果多项式的表示和a,b的规则一样，从最高次项到最低次项，不要包含系数为0的项。但是如果结果多项式等于0（即有且仅有常数项0）则需要包含该项。计算过程中涉及的整数加法不会溢出。


### 测试说明

平台会对你编写的代码进行测试：

测试输入：
`3 2 -1 0 0 -1`
`1 5 -3 2 -1 0 0 -1`
输入说明：
第一个多项式为3x^2-1
第二个多项式为x^5-3x^2-1
预期输出：
`1 5`
`-2 0`
输出说明：
结果多项式为x^5-2

### 代码样例(By 李瑞)

```cpp
#include<iostream>
using namespace std;

struct Node {
	int order, coeff;//order是次数，coeff是系数
	Node *nxt;
};

Node* add_poly(Node* a, Node* b)
{
	Node *re = new Node;
	int x[666] = { 0 };//由于不会链表相关操作，考虑用数组存储数据，便于操作,并且可以起到直接合并的效果
	while (a != nullptr)//分别将两个链表存入数组
	{
		x[a->order] += a->coeff;
		a = a->nxt;
	}
	while (b != nullptr)
	{
		x[b->order] += b->coeff;
		b = b->nxt;
	}
	Node *c = new Node;
	Node *d;
	for (int i = 665; i >= 0; i--)//寻找最大次数项
	{
		if (x[i]!=0)
		{
			d = new Node;
			d->coeff = x[i];
			d->order = i;
			if (c->coeff == 0)//将第一个非0项作为开头
			{
				c = d;
				re = c;
			}
			else//将表连上
			{
				c->nxt = d;
				c = d;
			}
		}
	}
	c->nxt = nullptr;
	return re;
}

int main()
{
	Node *a = nullptr, *pa = nullptr, *b = nullptr, *pb = nullptr;
	int coef, orde;
	cin >> coef >> orde;//传入第一个链表
	while (orde >= 0) {
		Node* na = new Node;
		na->order = orde;
		na->coeff = coef;
		na->nxt = nullptr;
		if (pa) pa->nxt = na;
		pa = na;
		if (a == nullptr) a = pa;
		cin >> coef >> orde;
	}
	cin >> coef >> orde;//传入第二个链表
	while (orde >= 0) {
		Node* nb = new Node;
		nb->order = orde;
		nb->coeff = coef;
		nb->nxt = nullptr;
		if (pb)  pb->nxt = nb;
		pb = nb;
		if (b == nullptr) b = pb;
		cin >> coef >> orde;
	}

	Node* c = add_poly(a, b);

	while (c) {
		cout << c->coeff << ' ' << c->order << endl;
		c = c->nxt;
	}

	//要不要补上a,b,c三个链表的删除？
	//看看能不能过，能过就不要
	return 0;
}
```



