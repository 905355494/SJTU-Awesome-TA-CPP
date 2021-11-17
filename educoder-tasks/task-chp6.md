```c    by:李旭东
#include<iostream>
using namespace std;

bool isPrime(int n)
{
	if(n==1)return 0;
    else if(n==2)return 1;
    else {
	for(int j=2;j<n;j++){
     if(n%j==0){
		  return 0;
		  break;
	  }
      if(j==n)return 1;
	 }
	}
}

int main()
{
    int m,n,cnt=0;
	int i;
	cin>>m;
	cin>>n;
	for(i=m;i<=n;++i){
        if(isPrime(i))
		   cnt++;
	}
    cout<<cnt;
	return 0;
}
```
```c
#include<iostream>
using namespace std;

bool perfectNumber(int i)
{
	int s=0;
	for (int j=2;j<i;++j){
		if(j==i)return 0;
		if(i%j==0){
			s+=j;
		}
	}
	if (i==1)return 0;
	else if(s==i-1)return 1;
	else return 0;
}
int main()
{
    int m,n,cnt=0;
	cin>>m;
	cin>>n;
	for(int i=m;i<=n;++i){
		if(perfectNumber(i)){
		cnt++;
		cout<<i<<" ";}
	}
    if (cnt==0)
	cout<<"-1";
	return 0;
}
```
```c
#include<iostream>
#include<cstring>
using namespace std;
const int MAXSIZE = 10000;

void  printInt(int n,int base){
    int i = 0;
   int s[MAXSIZE] = { 0 };
    while (n != 0){
        s[i] = n % base;
        n= n / base;
        i++;
    }
    for (; i > 0; i--)     
    {
        if (s[i - 1] > 9 && s[i - 1] <= 15)
            cout << (char)(s[i - 1] + 55);          
        else if (s[i - 1] > 15 && s[i - 1] <= 61)
            cout << (char)(s[i - 1] + 61);          
        else
            cout << s[i - 1];          
    }

}
int main()
{
    int n,base;
    cin>>n;
    cin>>base;
    printInt(n,base);
	return 0;
}

```
```c
#include<iostream>
using namespace std;

void valid(int n){
	int b[10000];
	b[0] = n;
	int i = 1;
	while (n > 1)
	{
		if (n % 2 == 1)
		{
			n = n * 3 + 1;
		}
		else
		{
			n = n / 2;
		}
		b[i++] = n;
	}
	cout<<b[0];
	for (int j = 1; j <i; j++)
	{
		cout << " "<< b[j] ;
	}
}
int main()
{
    int n;
	cin >> n;
	valid(n);

	return 0;
}
```
```c
#include <iostream>
#include "string.h"
using namespace std;


template <class T> 
void maxmin(T* x, int n)//函数模板  
{  
    T tempmax = x[0];  
    T tempmin = x[0];  
    for (int i = 1; i < n; i++)  
    {  
        if (x[i] > tempmax)tempmax = x[i];  
        if (x[i] < tempmin)tempmin = x[i];  
    }  
    cout<<tempmax<<" "<<tempmin<<endl; 
}  
  
int main()
{
    int m, n;
    int arr_int[10000];
    double arr_double[10000];

    // 输入m和整型数组
    cin >> m;
    for(int i = 0; i < m; i++)
        cin >> arr_int[i];

    // 输入n和浮点型 数组
    cin >> n;
    for(int i = 0; i < n; i++)
        cin >> arr_double[i];
    // 输出结果
    maxmin(arr_int, m);
    maxmin(arr_double, n);
    return 0;
}

```
```c
#include<iostream>
#include<algorithm>
using namespace std;

int  swim(int p[1000],int n){

    int T,T1=0,T2=0;
    int i=0;
    if(n==1)T=p[0];
    else if(n==2)T=p[0]+p[1];
    else if(n==3)T=p[0]+p[1]+p[2];
    else {
        int i=0;
      if (n%2==0){
        do{
           T1=T1+2*p[1]+p[n-1-2*i]+p[0];
           T2=T2+(2*p[0]+p[n-1-2*i]+p[n-2-2*i]);
           i++;
        }while((n-1-2*i)>1);
        T1+=p[1];
        T2+=p[1];
        if(T1<T2)T=T1;
        else T=T2;
      }
     else{
        do{
            T1=T1+2*p[1]+p[n-1-2*i]+p[0];
            T2=T2+(2*p[0]+p[n-1-2*i]+p[n-2-2*i]);
            i++;
        }while((n-1-2*i)>3);
        T1+=(p[0]+p[2]+p[1]);
        T2+=(p[0]+p[2]+p[1]);
        if(T1<T2)T=T1;
        else T=T2;
    }
    
    }
    return T;
}
int main()
{
   	int n,p[1000],i;
    cin>>n;
    for(i=0;i<n;i++) cin>>p[i];
    sort(p,p+n);
    cout<<swim(p,n);
    return 0;
}

```



```cpp

```
```cpp

```
```cpp

```
```cpp

```
```cpp

```
```cpp

```
