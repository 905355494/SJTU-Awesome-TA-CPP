

```c
#include <iostream>
using namespace std;

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
        if (a[i]%2==1) {cout<<i<<" ";}
    }
    return 0;
}
```


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


```c
#include <iostream>
#include<cmath>
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


```c
#include<bits/stdc++.h>
using namespace std;
int n,mx=-1,id;
int main() {
	cin>>n;
	for(int i=0,cnt;i<n;++i) {
		for(int a,j=cnt=0;j<n;++j) cin>>a,cnt+=a;
		if(cnt>mx) mx=cnt,id=i;
	}
	cout<<id;
    return 0;
}
```


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
