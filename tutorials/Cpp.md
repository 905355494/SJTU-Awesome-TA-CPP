# [C++编程问题汇总【不断更新】](https://github.com/OneForward/TACpp/blob/master/tutorials/Cpp.md)

> 遇到了任何问题都不要慌张，
> 1. 上机的时候向助教询问
> 2. QQ群里主动提问或者私聊助教询问
> 3. 微信群里询问
> 4. 百度搜索你遇到的问题


- [C++编程问题汇总【不断更新】](#c编程问题汇总不断更新)
  - [Q & A](#q--a)
  - [C++语法问题](#c语法问题)
  - [变量或者对象的生存期与内存管理](#变量或者对象的生存期与内存管理)

## Q & A
#### 1. `int` 和 `short` 都是4字节, 面对一个4字节是否有一个机制能区分它是什么类型（比如存在不同的地方）？

  事实是，类型系统其实是为编译器服务的，用于类型推导、类型检查、组合类型、继承、派生等等，用于检查代码正确性、简化代码。而编译器做好这些类型检查的工作后，转到机器语言时，它们都脱掉了类型这个帽子，而只是单纯的寄存器变量罢了。因此程序在 运行 期间 ，没有 类型 这个约束。在 CPU 看来，`int` 变量只是存储在寄存器上的4字节的值。

  对于机器来说，它只知道命令和对象，并不知道4字节对象是`float`还是`int`。但是指令是有针对性的。譬如整型加法是`ADD`，浮点加法是`ADDSD`之类的。因此，编译器只需要将变量要执行的运算翻译成对应于其类型的机器指令，而对于机器而言，无需再为“类型”去额外存储信息了。

#### 2. 为什么不同计算机能运行同一个C++程序，而不能运行同一个汇编程序?

  汇编语言使用的指令往往是和机器的硬件的体系结构有关，譬如x64和arm平台的机器指令都是不同的。具体细节可以等学了嵌入式这门课就知道了。

#### 3. `main` 函数是啥？其参数是干啥的？

程序应当含有一个名为 main 的全局函数，它被指定为程序的启动点。它应当有下列形式之一：

```cpp
int main () { body }	(1)	
int main (int argc, char *argv[]) { body }	(2)	

argc	-	非负数，表示从程序运行的环境传递给程序的实参个数。
argv	-	指针，指向包含 argc + 1 个指针的数组的首元素。数组末元素为空指针，若其前面有任何元素，则它们指向空终止多字节字符串，表示从执行环境传递给程序的若干参数。若 argv[0] 不是空指针，或等价地 argc > 0 ，则它指向表示用于调用程序的名称的字符串，或空字符串。
body	-	main 函数的函数体
```


因此，main 函数的参数可以用于为编译后的程序传递命令行参数。


## C++语法问题

- 引用自己实现的头文件应使用双引号而非尖括号

  ```c++
  #include "my_headers.h" // OK
  ```

- 指针的声明问题。

  ```c++
  Node* p1, p2, p3; // 注意p2, p3类型不是 Node*
  ```

- `cin.get()`, `cin.getline()` , `cin >>` 问题。

  OJ上一般不推荐使用 `cin.get()` ，理由是get遇到界定符时,停止执行,但并不从流中提取界定符（如换行符）,再次调用会遇到同一个界定符,函数将立即返回,不会提取输入，导致程序运行异常。   

- 数组如何作为函数参数。

  数组做参数时会直接被隐式转化为指针。如下声明是等价的

  ```c++
  void f(int []);
  void f(int *);
  ```

  虽然也可以写出数组大小 `void f(int [10]);`，但是不推荐。二维数组有`void f(int [][10])`的写法，亦不推荐。

- 函数默认参数问题。

  C++规定默认参数只能在声明或者定义中出现一次。一般建议将默认参数写在声明中。

  ```c++
  struct Array {
  	Array(int capacity=10);
  };
  
  Array::Array(int capacity=10) {} // 错误
  Array::Array(int capacity) {} // OK
  ```

  

- 函数存在无返回值的可能性。

  忘记写返回，如**赋值运算符重载忘记返回*this**。或者**没有管辖到条件分支的所有情况**。

  ```c++
  int f(int x) {
  	if (x == 0) return 0;
      // warning: control reaches end of non-void function [-Wreturn-type]
  }
  ```

- 前置函数声明，在后面实现函数时，函数签名不匹配。(`const`，`&`修饰符)

  例如

  ```c++
  // 前置的函数声明
  bool search(const int&) const;

  // 后置函数实现
  // void search(const int&) const {...}; 错误，函数签名不匹配
  // bool search(int&) const {...}; 错误，函数签名不匹配
  // bool search(const int) const {...}; 错误，函数签名不匹配
  // bool search(const int&) {...}; 错误，函数签名不匹配
  bool search(const int&) const {...}; // OK
  ```

- C++的赋值都是值传递。体会差别：

  ```c++
  struct Node { 
      int data;
  	Node* next;
      Node(int d=0): data(d) {}
  };
  
  Node* head = new Node();
  
  // method 1
  Node* next = head->next; next = new Node(); 
  ```

  与

  ```c++
  // method 2
  head->next = new Node();
  ```

  只有方法2可以正确的构造新节点。

- 无法使用`nullptr`等。

  可以在编译选项中开启`-std=c++11`。

- 一般建议模板类的实现和声明写在同一个文件里，不分开成两个文件写。

 很多同学问过这个问题。例如

```c++
// file Array.h
template<class T> class Array {
	T* data;
	int capacity;
public:
	Array(int capacity=10);
};
```

```c++
// file Array.cpp

#include "Array.h"
template<class T> Array<T>::Array(int capacity) {
	data = new T[capacity];
}
```

```c++
// file main.cpp

#include "Array.h"
int main() {
	Array<int> A; // failed!
}
```

这里错误的原因时编译的时候每个`.cpp`是独立编译然后链接的。头文件不会被编译，只会做预处理，然后附在 `.cpp`编译后的文件中。因此编译 `main.cpp` 的时候只看见头文件，没有看见实现，也就不知道模板实例如何实现。最终导致 `main.exe` 调用时找不到模板实例的实现。有两种解决方法

1. 将Array的实现和声明都写在一个头文件里，这样 `main` 就可以看到模板实现了。

2. 在实现中显示地添加需要的模板实例，例如

   ```c++
   // file Array.cpp
   
   #include "Array.h"
   template<class T> Array<T>::Array(int capacity) {
   	data = new T[capacity];
   }
   
   template class Array<int>; // 显示添加模板实例
   ```

- 继承抽象基类时，没有将该抽象基类所有的纯虚成员重新实现。

  ```c++
  class List {
  public:
      virtual int size() const = 0; // pure virtual function 
      virtual ˜List() {} // destructor 
  };

  class Stack: public List {
  public:
      // 忘记定义和实现 int size() const ...
  };
  ```



- 定义某个继承类时，基类必须已经实现，且继承类应在定义时实现。

  ```c++
  struct List; 
  strcut LinkList: public List {}; // 错误，基类没有实现
  ```

  ```c++
  struct List {}; 
  strcut LinkList: public List; // 错误，继承类没有在定义处实现
  ```

- 访问内嵌类。

  ```c++
  struct List {
      struct Node { };
  };
  
  typename List::Node* pNode = new typename List::Node;
  ```
  
  
  


## 变量或者对象的生存期与内存管理

- 变量或者对象的值没有初始化，或者类内某些成员没有初始化。
- 对象delete后没有将对应的指针赋值为`nullptr`或`NULL`，造成后续的判空问题。
- 定义数组时，数组大小使用变量。
- 数组没有初始化却被访问。（可能引发**SIGSEGV**内存异常的中断）
- 数组越界访问。（可能引发**SIGSEGV**中断）

```c++
int N; cin >> N; int arr[N];  // 错误，数组大小不应该使用变量。这样的处理方式可能会有内存问题。

class List {
    ...
public:
    ...
    int getMax() const {
        int max; // max 忘记初始化
        for ...
    }
};

int* data = new int[255];
visit(data[0]); // 没有初始化直接访问 data 数据


int* ptr = new int;
delete ptr; // delete后忘记置NULL
if (ptr == nullptr) { // 无法进入该分支
    ...
}
```



- 指针没有new就访问。此时指针值是随机值或者NULL，访问该位置的内存会引发**SIGSEGV**中断。

- 指针delete后再被访问或者再试图delete。此时指针值所在的内存位置已经没有对象，任何访问都将引发**SIGSEGV**中断。

  **对象在生存期内，可能被多个指针共享**。假如这些指针都是只读的(read-only)，则一点问题没有。但假若某个指针在某个地方对对象进行了写操作或者删除了对象，新手容易遗忘这件事，然后在别地方使用别的指针操作该对象时出错。

- 指针new完再new，程序没有记住第一次new出来的对象的地址，造成原来的对象悬浮。指针new完没有delete，这个对象会一直占用内存位置，直到程序结束时由系统回收。

  不过目前而言，这里只会造成内存浪费，对运行不影响。

```c++
int* p; // p points to random position of memory
*p = 1; // trouble


int* p1 = new int{99};
int* p2 = p1; // potential trouble
delete p1; // now p2 doesn’t point to a valid object
p1 = nullptr; // gives a false sense of safety
*p2 = 999; // this may cause trouble


int* p3 = new int{99}; // object1
p3 = new int{99}; // p3 points to object2, and object1 is dangling
``` 
