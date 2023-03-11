#                                NHẬP XUẤT TRONG C++





Việc nhập xuất là việc cơ bản nhất trong competitive programming, bất kể một bài toán nào đều có input và output. Mình xin giới thiệu với các bạn các cách nhập xuất hay dùng



Dòng lệnh chuẩn để vào ra file khi đề có yêu cầu sử dụng vào ra bằng file

```c++
freopen("input.txt", "r", stdin);
freopen("output.txt", "w", stdout);
```

```c--
#include <iostream>
using namespace std;
int main()
{
freopen("INPUT.TXT", "r", stdin);
freopen("OUTPUT.TXT", "w", stdout);
int x;
cin >> x;
cout << x;
return 0;
}
```

Ví dụ 1:

![image](https://user-images.githubusercontent.com/42260182/131367468-448aea80-ae09-47d5-aa52-ba211acac902.png)





* Lưu ý nhỏ là khi đọc đề bài các bạn nên đặt biến giống với yêu cầu đề bài.

```c++
#include<iostream>
using namespace std;

int main()
{
    int n,k;
    cin>>n>>k;
    int x,y;
    cin>>x>>y;
    int a[n+1],b[n+1];
    for(int i=0;i<n;i++)
    {
        cin>>a[i]>>b[i];
        //hoặc các bạn có thể nhập như sau
        //int u,v;
        //cin>>u>>v;
    }
}
```







Ví dụ 2: 

Đề bài này yêu cầu vào ra bằng file nên chúng ta sẽ sử dụng cách đọc ghi giống như phần đầu

![image](https://user-images.githubusercontent.com/42260182/131368638-569231e2-2407-4212-baed-32d7e852fc17.png)





```c++
#include<iostream>
using namespace std;
int main()
{
    freopen("GAPMAT.INP", "r", stdin);
    freopen("GAPMAT.OUT", "w", stdout);
    
    string s;
    while(cin>>s)
    {
        //code
    }
}
```





Ví dụ 3:



![image](https://user-images.githubusercontent.com/42260182/131371817-26084d43-6445-49a0-a94e-90f26be3ca0e.png)



```c++
#include<iostream>
using namespace std;
int main()
{
    int n;
    while(cin>>n)
    {
        //code here
    }
}
```





Ví dụ 4:

![image](https://user-images.githubusercontent.com/42260182/131371683-a84bb6e6-58b7-453f-b856-c5ebd9b55bda.png)





```c++
#include<iostream>
using namespace std;
int main()
{
    freopen("TGV.INP", "r", stdin);
    freopen("TGV.OUT", "w", stdout);
    int n;
    cin>>n;
    int a[n+1];
    for(int i=0;i<n;i++)
        cin>>a[i];
}
```





Ví dụ 5:



![image](https://user-images.githubusercontent.com/42260182/131372176-fc72b521-b8ce-4c4c-9867-51ad7255623a.png)



```C++
#include<iostream>
using namespace std;
int main()
{
    freopen("CHIAQUA.INP", "r", stdin);
    freopen("CHIAQUA.OUT", "w", stdout);
    int n,k;
    cin>>n>>k;
    int a[n+1];
    for(int i=0;i<n;i++)
        cin>>a[i];
}
```





Ví dụ 6:

![image](https://user-images.githubusercontent.com/42260182/131373082-3ec898c4-a0ec-4d33-8edd-b086939ff5f8.png)



```c++
#include<iostream>
using namespace std;
int main()
{
    int m,n;
    cin>>m>>n;
  
    string s;
    for(int i=0;i<m;i++)
        cin>s;
}
```



ví dụ 7:



![image](https://user-images.githubusercontent.com/42260182/131375513-2275b219-e36a-4919-a793-e8cdca053b50.png)



* Với trường hợp có bộ test thì ta sẽ cần thêm 1 biến t để đọc bộ test rồi thực hiện như bình thường



```c++
#include<iostream>
using namespace std;
int main()
{
    int t;
    cin>>t;
    while(t--)
    {
        int n;
        cin>>n;
        long long a[n+1],b[n+1];
        for(int i=0;i<n;i++)
            cin>>a[i];
        for(int i=0;i<n;i++)
            cin>>b[i];
    }
}
```





Ví dụ 8:



```c++
input: 
anh tim noi nho
anh tim qua khu
nho lam ki uc anh va em
tra lai anh yeu thuong ay
xin nguoi hay tro lai noi day
```



```c++
  
#include<bits/stdc++.h>
using namespace std;
int main()
{
    int t;
    cin>>t;
    cin.ignore();
    while(t--)
    {
        string s;
        getline(cin,s);
    }
```

