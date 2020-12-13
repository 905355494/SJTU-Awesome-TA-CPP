# 实训作业参考答案 —— 第八章 数据封装-结构体



## 8.1 任务名称

时钟结构体

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

struct Clock{
    int hour;
    int minute;
    int second;
};

void setTime(Clock &myclock,int a,int b,int c){
    myclock.hour = a;
    myclock.minute = b;
    myclock.second = c;
}

void increase(Clock &myclock){
    int x=0,y=0;
    x = (myclock.second+1)/60;
    myclock.second = (myclock.second+1)%60;
    y = (myclock.minute+x)/60;
    myclock.minute = (myclock.minute+x)%60;
    myclock.hour = (myclock.hour+y)%24;
}

void showTime(const Clock &myclock){
    cout<<(myclock.hour>9?"":"0")<<myclock.hour<<":";
    cout<<(myclock.minute>9?"":"0")<<myclock.minute<<":";
    cout<<(myclock.second>9?"":"0")<<myclock.second<<endl;
}

int main()
{
    Clock myclock;
    int a,b,c;
    cin>>a>>b>>c;
    setTime(myclock,a,b,c);
    showTime(myclock);
    increase(myclock);
    showTime(myclock);
    cin>>a>>b>>c;
    setTime(myclock,a,b,c);
    showTime(myclock);
    increase(myclock);
    showTime(myclock);


    return 0;
}
```





## 8.2 任务名称

复数结构体

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
struct Compl{
    int a;
    int b;
};

void show(const Compl &mycompl){
    cout<<mycompl.a<<(mycompl.b>=0?"+":"")<<mycompl.b<<"i"<<endl;
}

Compl add(const Compl &compl1, const Compl &compl2){
    Compl result;
    result.a = compl1.a+compl2.a;
    result.b = compl1.b+compl2.b;
    return result;
}

Compl mul(const Compl &compl1, const Compl &compl2){
    Compl result;
    result.a = compl1.a*compl2.a-compl1.b*compl2.b;
    result.b = compl1.a*compl2.b+compl1.b*compl2.a;
    return result;
}

int main()
{
    Compl myc1,myc2,result;
    cin>>myc1.a>>myc1.b>>myc2.a>>myc2.b;
    cout << "x = ";
    show(myc1);
    cout << "y = ";
    show(myc2);
    myc1 = add(myc1,myc2);
    cout<<"x += y; x = ";
    show(myc1);
    myc2 = mul(myc2,myc1);
    cout<<"y *= x; y = ";
    show(myc2);
    cout<<"x + y = ";
    show(add(myc1,myc2));
    cout<<"y * x = ";
    show(mul(myc2,myc1));
     cout << "x = ";
    show(myc1);
    cout << "y = ";
    show(myc2);
    return 0;
}
```





## 8.3 任务名称

通讯录结构体

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
struct Compl{
    int a;
    int b;
};

void show(const Compl &mycompl){
    cout<<mycompl.a<<(mycompl.b>=0?"+":"")<<mycompl.b<<"i"<<endl;
}

Compl add(const Compl &compl1, const Compl &compl2){
    Compl result;
    result.a = compl1.a+compl2.a;
    result.b = compl1.b+compl2.b;
    return result;
}

Compl mul(const Compl &compl1, const Compl &compl2){
    Compl result;
    result.a = compl1.a*compl2.a-compl1.b*compl2.b;
    result.b = compl1.a*compl2.b+compl1.b*compl2.a;
    return result;
}

int main()
{
    Compl myc1,myc2,result;
    cin>>myc1.a>>myc1.b>>myc2.a>>myc2.b;
    cout << "x = ";
    show(myc1);
    cout << "y = ";
    show(myc2);
    myc1 = add(myc1,myc2);
    cout<<"x += y; x = ";
    show(myc1);
    myc2 = mul(myc2,myc1);
    cout<<"y *= x; y = ";
    show(myc2);
    cout<<"x + y = ";
    show(add(myc1,myc2));
    cout<<"y * x = ";
    show(mul(myc2,myc1));
     cout << "x = ";
    show(myc1);
    cout << "y = ";
    show(myc2);
    return 0;
}

```





## 8.4 任务名称

矩阵结构体

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

```



## 8.5 任务名称

改错题

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

    cin >> num;
    if(num==-1) return 0;
    else{
        p = new List;
        head = p;
        p->num = num;
        p->next = NULL;
        cin>>num;
    }
    while(num != -1)
    {
        p = new List;
        p->num = num;
        p->next = head;
        head = p;
        cin >> num;
    }

    for(p = head; p != NULL; p = p->next)
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





## 8.6 任务名称

学生成绩管理程序

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

struct Student
{
    long long sid;
    char name[50];
    int grades[3];
};
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
    cin >> ws;
    cin.getline(s.name, 50);
    if (pos < n_students) return; // 更新已存在的学生时并不增加学生总数
    n_students++;
}
void change_data() {
    long long sid; cin >> sid;
    // 检查学生是否已存在
    int pos = 0;
    char w[100];
    while (pos < n_students && students[pos].sid != sid) pos++;
    if (pos >= n_students) cin.getline(w,100);
    else {
        Student& s = students[pos]; s.sid = sid;
        for (int i = 0; i < 3; ++i) cin >> s.grades[i];
        cin >> ws;
        cin.getline(s.name, 50);
        if (pos < n_students) return; // 更新已存在的学生时并不增加学生总数
        n_students++;
    }
}
int main()
{
    int type;
    long long temp;
    char tmp[50];
    Student t;
    bool flag;
    while (true)
    {
        cin >> type;
        switch (type)
        {
        case 1:insert_student(); break;
        case 2:change_data(); break;   
        case 3:
            cin >> temp;
            for (int i = 0; i < n_students; i++)
            {
                if (students[i].sid == temp)
                {
                    students[i].sid = 0; break;
                }
            }
            break;
        case 4:
            cin >> temp;
            for (int i = 0; i < n_students; i++)
            {
                if (students[i].sid == temp)
                {
                    cout << students[i].sid << " " << students[i].name << " " << students[i].grades[0] << " " << students[i].grades[1] << " " << students[i].grades[2] << " " << endl; break;
                }
            }
            break;
        case 5:
            bool f;
            cin >> ws;
            cin.getline(tmp, 50);
            for (int i = 0; i < n_students; i++)
            {
                f = true;
                for (int j = 0; tmp[j] != '\0'; j++)
                {
                    if (tmp[j] != students[i].name[j]) { f = false; break; }
                }
                if (f && students[i].sid != 0)
                {
                    cout << students[i].sid << " " << students[i].name << " " << students[i].grades[0] << " " << students[i].grades[1] << " " << students[i].grades[2] << " " << endl;
                }
            }
            break;
        case 6:
            for (int i = 1; i < n_students; i++)
            {
                flag = false;
                for (int j = 0; j < n_students - i; j++)
                {
                    if (students[j + 1].sid < students[j].sid)
                    {
                        t = students[j + 1]; students[j + 1] = students[j]; students[j] = t; flag = true;
                    }
                }
            }
            for (int i = 0; i < n_students; i++)
            {
                if (students[i].sid != 0)
                    cout << students[i].sid << " " << students[i].name << " " << students[i].grades[0] << " " << students[i].grades[1] << " " << students[i].grades[2] << " " << endl;
            }
            break;
        case 7:
            for (int i = 1; i < n_students; i++)
            {
                flag = false;
                for (int j = 0; j < n_students - i; j++)
                {
                    if (students[j + 1].grades[1] + students[j + 1].grades[2] + students[j + 1].grades[0] > students[j].grades[1] + students[j].grades[2] + students[j].grades[0])
                    {
                        t = students[j + 1]; students[j + 1] = students[j]; students[j] = t; flag = true;
                    }
                    else
                    if(students[j + 1].grades[1] + students[j + 1].grades[2] + students[j + 1].grades[0] == students[j].grades[1] + students[j].grades[2] + students[j].grades[0])
                {
                    if (students[j + 1].sid < students[j].sid)
                    {
                        t = students[j + 1]; students[j + 1] = students[j]; students[j] = t; flag = true;
                    }
                }
                }
            }
            for (int i = 0; i < n_students; i++)
            {
                if (students[i].sid != 0)
                    cout << students[i].sid << " " << students[i].name << " " << students[i].grades[0] << " " << students[i].grades[1] << " " << students[i].grades[2] << " " << endl;
            }
            break;

        }
        if (type == 0) break;

    }

    return 0;
}
```





## 8.7 任务名称

【附加题】反转链表

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

### 代码样例

```cpp
#include <iostream>

using namespace std;

struct ListNode {
    int val;
    ListNode *next;
};


ListNode* reverseList(ListNode* head) {
    /********* Begin *************/
    if(head==NULL) return head;
    else {
    ListNode*p,*q,*m;
    p=head;
    q=head->next;
    p->next=NULL;
    for(;q!=NULL;){
        m=q->next;
        q->next=p;
        p=q;
        q=m;
    }
    return p;

    }



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

void disp(ListNode* p) {
    while (p)
    {
        printf("%d -> ", p->val); p = p->next;
    }
    printf("nullptr\n");
}

int main()
{
    ListNode* L1 = createList(); disp(L1);
    ListNode* L2 = reverseList(L1); disp(L2);

    return 0;
}
```



## 8.8 任务名称

【附加题】约瑟夫环2

### 任务描述

约瑟夫问题（有时也称为约瑟夫斯置换），是一个出现在计算机科学和数学中的问题。在计算机编程的算法中，类似问题又称为约瑟夫环。

人们站在一个等待被处决的圈子里。 计数从圆圈中的指定点开始，并沿指定方向围绕圆圈进行。 在跳过指定数量的人之后，执行下一个人。 对剩下的人重复该过程，从下一个人开始，朝同一方向跳过相同数量的人，直到只剩下一个人，并被释放。

问题即，$$1, 2, ..., n$$ 这 $$n$$ 个数字排成一个圆圈，从数字1开始，每次从这个圆圈里删除第$$m$$个数字。求出这个圆圈里剩下的最后一个数字。


### 测试说明

【输入形式】$$n$$    $$m$$

【输出形式】一个整数

【样例输入】

`5 3`

【样例输出】

`4`

【样例说明】

例如，1、2、3、4、5这5个数字组成一个圆圈，从数字1开始每次删除第3个数字，则删除的前4个数字依次是3、1、5、2，因此最后剩下的数字是4。

【提示1】

$$n<=10000, m<=100000000$$

【提示2】
$$m$$ 可能远大于 $$n$$ ， 注意使用取模以加快算法。 

### 代码样例

```cpp
using namespace std;
struct link{
    int data;
    link *next;
};

int main()
{   int n,m,t=0,x;
    cin>>n>>m;
    link *head,*p,*q;
    
    head=p=new link;


    p->data=0;
    for (int i=1;i<n;i++){
        q=new link;
        q->data=i;
        p->next=q;
        p=q;
    }
    p->next=head;

    //报数删除
     p=head;
    for (t=n;p->next!=p;t--){
       
        x=m%t;
        if(x==0) x=t;
        if(x==1) x=t+1;
        if(x%2==0) {
            for(int i=1;i<=(x-2)/2;i++){
               q=p->next;
               p=q->next;
            }
               q=p->next;
               p->next=q->next;
               delete q;
               p=p->next;
        }
        else {
            for(int i=1;i<=(x-1)/2;i++){
            q=p->next;
            p=q->next;
            }
            q->next=p->next;
            delete p;
            p=q->next;
        }
    }

    cout<<p->data+1;

    return 0;
}
```



