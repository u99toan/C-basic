

#                                                        C++ CỞ BẢN



# 1. KIỂU DỮ LIỆU VÀ BIẾN



**Các kiểu dữ liệu thông dụng**

* Trong khi làm việc với bất kỳ ngôn ngữ lập trình nào ta cần phải sử dụng các kiểu biến đa dạng để lưu trữ thông tin.  Tùy vào yêu cầu đặt ra ta phải sử dụng biến thuộc kiểu dữ liệu nào đó phù hợp.

  ![image](https://user-images.githubusercontent.com/42260182/130307030-65471234-caca-41ad-b1c5-4a89772621d0.png)

  

  

  

  Như hình mô tả, có 2 kiểu dữ liệu: kiểu nguyên thủy (Primitive) và kiểu không nguyên thủy (Non-primitive). Ở phần này, ta chỉ xét đến các kiểu dữ liệu nguyên thủy (Primitive).

  

  

  

  

  ![image](https://user-images.githubusercontent.com/42260182/130306507-1bde0925-ac08-48fc-a2d4-3d6d23a7062f.png)



* Kiểu logic (Boolean): độ rộng: 1 byte; **trả về** một trong 2 giá trị đúng (true-1) hoặc sai (false-0); để **gán** giá trị cho một biến kiểu **bool**, ta có thể gán trực tiếp bằng chữ **true-false** hoặc giá trị **0** ứng với **false** và *các giá trị khác* **0** ứng với **true**. 

* Ngoài ra còn một kiểu dữ liệu là **void**; nó không trả về giá trị nào mà kết thúc hoạt động bằng cách hoặc chạm tới điểm kết thúc của hàm hoặc thực hiện một [lệnh trả về](https://vi.wikipedia.org/w/index.php?title=Lệnh_trả_về&action=edit&redlink=1) mà không có giá trị trả về. Kiểu dữ liệu này thường sử dụng trong các **Hàm**, sẽ được giới thiệu trong các phần sau. 







**BIẾN**

* Cú pháp khai báo trong C++

```c++
<kiểu dữ liệu> <tên biến> ;
hoặc <kiểu dữ liệu> <tên biến> = <giá trị khởi tạo> ;
```

Có thể khai báo nhiều biến cùng kiểu trên cùng một dòng, khi đó mối biến sẽ được ngăn cách bởi dấu phẩy.



Ví dụ khai báo:

```c++
int a; //khai báo kiểu số nguyên
float b; //khai báo kiểu số thực
long long c;// khai báo kiểu số nguyên dài với giá trị có thể lưu trữ trong khoảng +-10^18
char d; //khai báo kiểu kí tự 
string s; //khai báo kiểu xâu kí tự
double pi=3.14; //khai báo kiểu số thập phân
bool dung = true , sai = false; //khai báo kiểu boolean
```



**ÉP KIỂU TRONG C++**

Trong C++ ta không thể tính toán nếu chúng khác kiểu dữ liệu dẫn tới việc ta phải ép kiểu dữ liệu

cú pháp

```c++
Cú pháp: < (kiểu dữ liệu đích) > <giá trị>;
```



Ví dụ với bài toán cho 2 số nguyên x và y, tìm x/y.

```c++
int x=10;
int y=3;
cout<<x/y<<endl; //khi chưa ép kiểu: output: 3
cout<<(float)x/y<<endl; //output: 3.33333
cout<<x/(float)y<<endl; //output:3.33333 
```

Hoặc ngược lại, ta cũng có thể làm tròn số kiểu thập phân về kiểu nguyên:

```c++
float x=10.85982;
float y=2.9834;
cout<<x/y<<endl; output: 3.64008
cout<<(int)(x/y)<<endl; output: 3
cout<<(int)x/(int)y<<endl; output: 5
Cùng là ép kiểu về int, nhưng lí do vì sao output lại khác nhau? Hãy tự suy nghĩ và đưa ra kết luận nhé

```

**LÀM TRÒN SỐ THẬP PHÂN**

Một số bài toán liên quan tới số thập phân sẽ yêu cầu làm tròn tới 2,3.. chữ số sau dấu phẩy. Ví dụ với giá trị x=3,14159265 và yêu cầu làm tròn tới 4 chữ số thập phân:

Với ngôn ngữ C, ta có thể đơn giản in ra giá trị x với câu lệnh: printf(“%.4f”,x); thì với ngôn ngữ C++, ta phải dùng hàm 



```c++
setprecision trong thư viện <iomanip> với cú pháp: cout<<setprecision( <số chữ số thập phân cần hiển thị> )<<fixed<<giá trị;
double k=3.14159265;
cout<<setprecision(4)<<fixed<<k;
output: 3.1416
#hãy thử lại làm tròn tới 6 chữ số; làm tròn tới 12 chữ số; làm tròn tới 12 chữ số và bỏ đi đoạn <<fixed; cảm nhận kết quả.
```





**Lưu ý quan trọng**

Trong lập trình thi đấu, ngoài cách giải quyết bài bài toán (thuật toán) thì việc lựa chọn biến và kiểu dữ liệu cũng ảnh hưởng rất lớn tới kết quả của bài toán. Nếu dùng kiểu có miền giá trị quá lớn thì sẽ bị chiếm nhiều bộ nhớ, ngược lại, nếu dùng kiểu dữ liệu có miền quá nhỏ thì sẽ gây ra kết quả bị sai.



* Ví dụ: Viết chương trình nhập vào từ bàn phím N số nguyên A[i] (1<=N<=1000000), -10^9<=A[i]<=10^9. Tính tổng S của tất cả các số nguyên vừa nhập.
  * Với giá trị biến trong khoảng -10^9 đến 10^9 ta có thể sử dụng biến int để lưu trữ kết quả 
  * Với giá trị biến trong khoảng -10^12 đến 10^12 ta có thể sử dụng biến long để lưu trữ kết quả
  * với giá trị biến trong khoảng -10^18 đến 10^18 ta có thể sử dụng biến long long để lưu trữ kết quả và đây cũng là giá trị tối đa có thể biểu diễn được
  * Nếu muốn biểu diễn giá trị >10^18 ta phải chuyển sang biểu diễn bằng chuỗi và sẽ được học ở các bài số nguyên lớn





# 2.CẤU TRÚC RẼ NHÁNH, LẶP



## CẤU TRÚC RẼ NHÁNH





**If, else**

```c++
if( <điều kiện> ){
	khối câu câu lệnh khi điều kiện thỏa mãn;
}
else {
khối câu lệnh khi điều kiện không thoả mãn;
}
```



Ví dụ 1:  nhập một số nguyên a từ bàn phím, kiểm tra đó là số chẵn hay lẻ ?

```c++
#include <iostream>
using namespace std;
int main(){
    int a;
    cin>>a;
    if(a%2==0)
    {
        cout<<"a là số chẵn"<<endl;//đúng: kết luận
    }
    else
    {
        //sai:
        cout<<"a là số lẻ"<<endl;
    }
    return 0;
}
```





Ví dụ 2: nhập hai số nguyên a và b từ bàn phím, so sánh 2 số đó?

```c++
#include <iostream>
using namespace std;
int main()
{
    int a,b;
    cin>>a>>b;
    if(a>b) //kiểm tra xem a có lớn hơn b?
        cout<<"a lớn hơn b"<<endl;//đúng: kết luận
    else if(a<b)//a>b sai; kiểm tra a có nhỏ hơn b?
    {
        cout<<"a nhỏ hơn b"<<endl;
    }
    else//cả 2 điều kiện đều sai:
    {
        cout<<"hai số bằng nhau"<<endl;
    }
}

```



## CẤU TRÚC LẶP



A) Cấu trúc lặp

Có những công việc được lặp đi lặp lại nhiều lần với Cấu trúc IF-ELSE hay Cấu trúc switch – case ta khó mà giải quyết được. Tuy nhiên với cấu trúc vòng lặp, ta có thể dễ dàng giải quyết.

![image](https://user-images.githubusercontent.com/42260182/131211560-4fa5062c-d51f-4fc6-a049-a776a76cf74e.png)



**Vòng lặp while**

![image](https://user-images.githubusercontent.com/42260182/131211485-0f45c90f-bc47-40e9-ab8e-78f3acb561e1.png)



```c++
while(dieu_kien) 
{ 
  cac_lenh; 
}
```



Ở đây, cac_lenh có thể là lệnh đơn hoặc một khối các lệnh. dieu_kien có thể là bất kỳ biểu thức nào, và giá trị true là bất kỳ giá trị nào khác 0. Vòng lặp lặp đi lặp lại trong khi dieu_kien là true.

Khi điều kiện trở thành false, chương trình điều khiển ngay lập tức chuyển tới dòng lệnh ngay sau vòng lặp.



ví dụ:



```c++
#include <iostream> 
using namespace std; 
int main () 
{ 
   // Khai bao bien cuc bo: 
   int a = 4; 
   // vong lap while 
   while(a < 10) 
   { 
      cout << "Gia tri cua a la: " << a << endl; 
      a++; 
   } 
return 0; 
}
```





**Vòng lặp for**

Vòng lặp for trong C++ là một cấu trúc điều khiển lặp đi lặp lại mà cho phép bạn viết một vòng lặp một cách hiệu quả, mà cần thực hiện trong một khoảng thời gian cụ thể nào đó.

Cú pháp

```c++
for (bien; dieu_kien; tang_giam) 
{ 
  cac_lenh; 
}
```



Sơ đồ

![image](https://user-images.githubusercontent.com/42260182/131211599-78a9c035-b6eb-4872-8cb1-6fe0f922a227.png)

ví dụ:

```c++
#include <iostream> 
using namespace std; 
int main () 
{ 
    //Vòng lặp for 
    for(int a = 5; a < 15; a = a + 1) 
      { 
         cout << "Gia tri cua a la: " << a << endl; 
      } 
return 0; 
}
```





**Vòng lặp do-while**

Không giống như các vòng lặp for và while, mà kiểm tra điều kiện vòng lặp ở ngay bước đầu tiên của vòng lặp, vòng lặp do…while trong Ngôn ngữ C++ kiểm tra điều kiện của nó tại phần cuối của vòng lặp.

Một vòng lặp do…while là tương tự như vòng lặp while, ngoại trừ ở điểm một vòng lặp do…while bảo đảm thực hiện vòng lặp ít nhất một lần.



Cú pháp

```cpp
do {cac_lenh;}
while(dieu_kien);
```



Sơ đồ:

![image](https://user-images.githubusercontent.com/42260182/131211627-647cf8e6-027b-4cc0-b9d1-1d3fc2df676f.png)



Ví dụ:



```c++
#include <iostream> 
using namespace std; 
int main () 
{ 
   // Khai bao bien cuc bo: 
   int a = 5; 
   // Vong lap do...while 
   do 
      { 
        cout << "Gia tri cua a la: " << a << endl; 
        a = a + 1; 
      }while( a < 15 ); 
return 0; 
}
```



**Lồng vòng lặp trong C++**

Cú pháp

```cpp
for (bien; dieu_kien; tang_giam) 
{ 
   for (bien; dieu_kien; tang_giam) 
   { 
      cac_lenh;
   } 
   cac_lenh; 
   // ban co the dat nhieu lenh tai day. 
}
```



Cú pháp để **lồng vòng lặp while** trong C++ như sau:

```cpp
while(dieu_kien) 
{ 
   while(dieu_kien) 
   { 
      cac_lenh; 
   } 
   cac_lenh; 
   // ban co the dat nhieu lenh tai day. 
}
```

Cú pháp để **lồng vòng lặp do...while** trong C++ như sau:

```cpp
do 
{ 
   cac_lenh; 
   // ban co the dat nhieu lenh tai day. 
   do 
   { 
      cac_lenh; 
   }while(dieu_kien); 
}while(dieu_kien);
```





**Ví dụ**

Chương trình sau sử dụng lồng vòng lặp for để tìm các số nguyên tố từ 2 đến 50:



```cpp
#include <iostream> 
using namespace std; 
int main () 
{
   int i, j; 
   for(i=2; i<50; i++) { 
      for(j=2; j <= (i/j); j++) 
         if(!(i%j)) break; // neu tim thay he so, thi khong la so nguyen to 
         if(j > (i/j)) cout << i << " la so nguyen to\n"; 
   } 
return 0; 
}
```

### Lệnh break trong C++

Lệnh break trong C++ có hai cách sử dụng:

Khi lệnh break được sử dụng trong vòng lặp, vòng lặp ngay lập tức kết thúc và điều khiển chương trình bắt đầu lệnh tiếp theo sau vòng lặp.

Nó có thể được sử dụng trong lệnh switch (sẽ được nhắc đến trong chương tới).

Nếu bạn đang sử dụng các vòng lặp lồng nhau (ví dụ, một vòng lặp bên trong vòng lặp khác), lệnh break sẽ dừng thực thi một lệnh nào đó trong một vòng lặp và bắt đầu thực thi lệnh tiếp theo của đoạn code sau khối code đó.

**Cú pháp**

Cú pháp của lệnh break trong C++ như sau:

```c++
break;
```



![image](https://user-images.githubusercontent.com/42260182/131212436-9e6705c9-3181-41d2-b099-6bfadb2fbe6d.png)



```cpp
#include <iostream> 
using namespace std; 
int main () 
{ 
   // Khai bao bien cuc bo: 
   int a = 10; 
   // Vong lap do...while 
   do 
   { 
      cout << "Gia tri cua a la: " << a << endl; 
      a = a + 1; 
      if(a > 15) 
      { 
         // Ket thuc vong lap 
         break; 
      } 
   }while(a < 20); 
   return 0; 
}
```

### Lệnh continue trong C++

Lệnh continue trong C++ làm việc hơi giống với lệnh break. Thay vì bắt buộc kết thúc, nó bắt buộc vòng lặp tiếp theo diễn ra, bỏ qua bất kỳ đoạn code nào ở giữa.

Với vòng lặp for, lệnh continue làm cho bước kiểm tra điều kiện và phần tang_giam của vòng lặp thực thi. Với while và do…while, lệnh continue làm điều khiển chương trình chuyển tới các kiểm tra điều kiện.

**Cú pháp**

Cú pháp của lệnh continue trong C++ như sau:

```
continue;
```

![image](https://user-images.githubusercontent.com/42260182/131212450-bce11107-2830-4608-b492-20ddbf9b26a6.png)



```cpp
#include <iostream> 
using namespace std; 
int main () 
{ 
    // Khai bao bien cuc bo:   
    int a = 10; 
    // vong lap do...while 
    do 
    { 
       if(a == 15) 
       { 
          // nhay qua buoc lap. 
          a = a + 1; 
          continue; 
       } 
       cout << "Gia tri cua a la: " << a << endl; 
       a = a + 1; 
    }while(a < 20); 
    return 0; 
}
```





**Cú pháp**

Cú pháp của lệnh goto trong C++ như sau:

```cpp
goto label; 
.. 
. 
label: lenh;
```

Ở đây, label có thể là bất kỳ phần thuần văn bản nào ngoại trừ các từ khóa trong C++, và nó có thể được thiết lập bất cứ đâu trong chương trình C++, bên trên hoặc dưới lệnh goto này.

![image](https://user-images.githubusercontent.com/42260182/131212473-c599ce60-85b2-4249-b81c-5aafaa04fb8f.png)





## Vòng lặp vô hạn trong C++



```cpp
#include <iostream> 
using namespace std; i
int main () 
{ 
     for( ; ; ) 
     { 
          cout<<("Vong lap nay se chay mai mai.\n"); 
     } 
     return 0; 
}
```



Hoặc

```c++
#include<iostream>
using namespace std;
int main()
{
    while(1)
    {
        cout<<"Vong lap nay se chay mai mai. \n";
    }
}
```











Các ví dụ bài tập về cấu trúc rẽ nhánh:

https://github.com/HungggPhan/exercises_part1?fbclid=IwAR0hT1o7xHN1aGkPSDiYw9-C8sf6T_qA4p4ny6RjpKMEN1rrSOkAYXMdJkA





# 3. MẢNG, CON TRỎ

**Mảng 1 chiều**



Ở các bài học trước chúng ta đã cùng tìm hiểu về biến được dùng để lưu trữ giá trị trong bộ nhớ. Giả sử chúng ta cần lưu trữ 1000 số nguyên trong bộ nhớ, thì chúng ta sẽ khai báo đúng 1000 tên biến khác nhau. Điều này rất là kinh khủng, chúng ta phải suy nghĩ làm sao cho 1000 tên biến phải có nghĩa. Trong C++, mảng sẽ giúp chúng ta giải quyết khó khăn trên.

Khai báo mảng: 

<Kiểu dữ liệu> <Tên mảng>[<Kích thước mảng>]

ví dụ: int a[1001];

char c[18];

Lưu ý: chỉ số mảng bắt đầu từ 0 và kết thúc bằng [SIZE-1].



![image](https://user-images.githubusercontent.com/42260182/131212702-72ccdcef-ebfa-4338-b61a-7e8e607abcfc.png)



ví dụ 1:

```c++
#include <iostream>
 
using namespace std;
 
int main() {
    int i = 0;
    int a[5];  // khai bao mang
    a[0] = 80; // khoi tao mang
    a[1] = 60;
    a[2] = 70;
    a[3] = 85;
    a[4] = 75;
    //co the khai bao nhu sau: int a[5]={80,60,70,85,75};
    for (i = 0; i < 5; i++) {
        cout << a[i] << endl;
    }
    return 0;
}

```



ví dụ 2:

Nhập mảng trong c++:

 cho mảng a gồm n phần tử, viết chương trình in ra các phần tử đã nhập từ bàn phím?

```c++
#include <iostream>
using namespace std;
int main(){
    int n;
    cout<<"nhap so phan tu: ";
    cin>>n;
    int a[n]; 
    cout<<"\nnhap cac phan tu cua mang: "<<endl;
    for(int i=0;i<n;i++){
        cout<<"nhap a["<<i<<"]: ";
        cin>>a[i]; 
    } 
    cout<<"\ncac phan tu cua mang a la:"<<endl;
    for(int i=0;i<n;i++){
        cout<<"a["<<i<<"] = "<<a[i]<<endl; 
    } 
    return 0; 
} 

```







### Mảng 2 chiều trong C++



![image](https://user-images.githubusercontent.com/42260182/131212809-fdcec8bd-72a5-4199-b885-3d49e8649e76.png)





Khai báo

```c++
kieu_du_lieu ten_mang [x][y];
```



Khởi tạo

```c++
int a[3][4] = {
 {0, 1, 2, 3} , /* khoi tao gia tri cho hang ma co chi muc la 0 */
 {4, 5, 6, 7} , /* khoi tao gia tri cho hang ma co chi muc la 1 */
 {8, 9, 10, 11} /* khoi tao gia tri cho hang ma co chi muc la 2 */
};
```



```c++
int a[3][4] = {0,1,2,3,4,5,6,7,8,9,10,11};
```



**Truy cập các phần tử của mảng hai chiều trong C++**

Các phần tử mảng hai chiều được truy cập bởi sử dụng các chỉ số, ví dụ chỉ số hàng và chỉ số cột. Ví dụ:

```cpp
int val = a[2][3];
```

Lệnh trên sẽ truy cập vào phần tử thứ 4 từ hàng thứ 3 của mảng. Bạn có thể kiểm tra lại nó trong sơ đồ trên. Bây giờ chúng ta xem xét ví dụ dưới đây, chúng tôi đã sử dụng các vòng lặp lồng vào nhau để xử lý một mảng hai chiều:



```cpp
include <iostream>
using namespace std;
int main ()
{
  //mang sau co 5 hang va 2 cot.
  int a[5][2] = {{0,0}, {1,2}, {2,4}, {3,6},{4,8}};
  //hien thi gia tri cua cac phan tu trong mang
  for (int i = 0; i < 5; i++)
  for (int j = 0; j < 2; j++)
  {
  cout << "Gia tri cua a[" << i << "][" << j << "] la: ";
  cout << a[i][j]<< endl;
  }
return 0;
}
```





Ví dụ:

cho 2 số n và m, viết chương trình nhập vào và in ra mảng 2 chiều gồm n hàng và m cột



```c++
#include <iostream>
using namespace std;
int main(){
    int n,m; 
    cout<<"Nhap n,m: "; 
    cin>>n>>m; 
    int  a[n][m]; 
    cout<<"Nhap mang 2 chieu:\n"; 
    for(int i=0;i<n;i++){
        for(int j=0;j<m;j++){ 
            cin>>a[i][j]; 
        }
    } 
    cout<<"Mang da nhap la:\n"; 
    for(int i=0;i<n;i++) {
        for(int j=0;j<m;j++){
            cout<<a[i][j]<<" "; 
        } 
        cout<<endl; 
    }
} 

```







**Con Trỏ**

Một con trỏ là một biến mà trong đó giá trị của nó là địa chỉ của biến khác. Như bạn biết, mỗi biến được lưu trong một vùng nhớ nhất định và mỗi vùng nhớ này có địa chỉ được định nghĩa để dễ dàng trong việc truy cập tới biến đó. Ta có thể sử dụng toán tử (&) tương ứng với địa chỉ của nó trong bộ nhớ. Xem xét ví dụ dưới đây, sẽ in ra địa chỉ của biến được định nghĩa:



```c++
#include <iostream>
 
using namespace std;
 
int main ()
{
   int  bien1;
   char bien2[10];
 
   cout << "Dia chi cua bien1 la: ";
   cout << &bien1 << endl;
 
   cout << "Dia chi cua bien2 la: ";
   cout << &bien2 << endl;
 
   return 0;
}
Kết quả:
Dia chi cua bien1 la: 0x6ffe4c
Dia chi cua bien2 la: 0x6ffe40

```

Lưu ý: khi chạy chương trình trên, kết quả trả về địa chỉ của bien1 và bien2 có thể khác đi.

 

Giống như các biến và hằng số, bạn phải khai báo con trỏ trước khi bạn có thể sử dụng nó để lưu trữ bất kì địa chỉ của biến nào.

Cú pháp khai báo con trỏ: <Kiểu dữ liệu> *<Tên con trỏ>; 

 

ví dụ: 

```c++
int  *ip;  // trỏ tới một số int
double *dp;  // trỏ tới một số double
float *fp;  // trỏ tới một số float
char  *ch   // trỏ tới một ký tự
```



Kiểu dữ liệu thực sự của giá trị của tất cả các con trỏ, có thể là integer, float, character, hoặc kiểu khác là một số long hệ hexa biểu diễn một địa chỉ bộ nhớ.

 

Con trỏ được sử dụng theo hai cách: Dùng con trỏ để lưu địa chỉ của biến để thao tác và lấy giá trị của biến do con trỏ trỏ đến để thao tác.

\+ Cách 1: Dùng con trỏ để lưu địa chỉ của biến để thao tác:

Bản thân con trỏ sẽ được trỏ vào địa chỉ của một biến có cùng kiểu dữ liệu với nó. Cú pháp của phép gán như sau: <Tên con trỏ> = &<Tên biến>;

Trong phép toán này, tên con trỏ không có dấu “*”. Ví dụ:

```c++
int x, *ip;
ip = &x;
```



Ở đây, con trỏ ip có kiểu int trỏ vào địa chỉ của biến x có kiểu nguyên. Phép toán &<Tên biến> sẽ cho địa chỉ của biến tương ứng.

\+ Cách 2: Lấy giá trị của biến do con trỏ trỏ đến:Phép lấy giá trị của biến do con trỏ trỏ đến được thực hiện bằng cách gọi tên: *<ten_con_tro>;

 Trong phép toán này, phải có dấu con trỏ “*”. Nếu không có dấu con trỏ, sẽ trở thành phép lấy địa chỉ của biến do con trỏ trỏ tới. Ví dụ:



```c++
int x = 12, y, *ip;
ip = &y; //ip trỏ tới địa chỉ của biến y
int x = 12, y, *ip;
ip = &y; //ip trỏ tới địa chỉ của biến y
```





Sau đây là chương trình sử dụng thao tác con trỏ với hai cách trên



```c++
#include <iostream>
using namespace std;
int main () {
int  x = 20, y;    // khai bao bien binh thuong
int  *p;          // bien con tro
p = &y;
*p = x;           // dia chi luu tru cua bien con tro
// in dia chi luu tru cua bien con tro p
cout << "Dia chi luu tru cua bien con tro p: ";
cout << p << endl;
// gia tri cua dia chi o nho cua con tro
cout << "Gia tri cua bien *p: ";
cout << *p << endl; 		
// gia tri cua bien x
cout << "Gia tri cua bien x: ";
cout << x << endl;  
// gia tri cua bien y	
cout << "Gia tri cua bien y: ";
cout << y<< endl;
 	return 0;
}


Kết quả sau khi chạy chương trình: 
Dia chi luu tru cua bien con tro ip: 0x6ffe3c
Gia tri cua bien *ip: 20
Gia tri cua bien x: 20
Gia tri cua bien y: 20

```

Ngoài địa chỉ bộ nhớ ra, còn có một giá trị khác mà con trỏ có thể giữ: đó là giá trị null. Giá trị null là một giá trị đặc biệt, có ý nghĩa là con trỏ đang không trỏ đến bất cứ thứ gì. Một con trỏ chứa giá trị null được gọi là con trỏ null. Trong C++, chúng ta có thể gán giá trị null cho một con trỏ bằng cách khởi tạo hoặc gán cho nó giá trị bằng 0. Con trỏ sẽ chuyển thành **boolean false** nếu chúng null, và boolean true nếu chúng không null.





# 4. String (chuỗi)

## Hạn chế của ngôn ngữ C



Trong ngôn ngữ lập trình C, chuỗi là một tập hợp các ký tự (char) được lưu trữ trên các ô nhớ liên tiếp và luôn luôn có 1 ký tự **null** là **\0** báo hiệu kết thúc chuỗi.

char c[] = "Hello C";

 

Ví dụ, khi khai báo và khởi tạo chuỗi theo cách trên, trình biên dịch sẽ tự thêm 1 ký tự null \0 vào cuối. Như vậy, nếu bạn muốn khai báo chuỗi để lưu n ký tự, bạn cần mảng ký tự có kích thước tối đa ít nhất là n+1.

Trong lập trình C: mảng các ký tự kết thúc bởi ký tự mã ASCII là 0 (ký tự ‘\0’) cùng với các hàm thư viện khai báo trong . Có nhiều bất tiện khi dùng theo cách thức này: 

\- Người lập trình phải chủ động kiểm soát bộ nhớ cấp phát cho chuỗi ký tự. Nói chung là phải am hiểu và rất thông thạo về kỹ thuật dùng bộ nhớ và con trỏ thì chương trình mới tránh được các lỗi về kỹ thuật; 

\- Không thể gán giá trị hay sử dụng phép toán + (ghép chuỗi) và các phép toán so sánh như: > (lớn hơn), < (nhỏ hơn),… mà phải gọi các hàm thư viện trong ; 

\- Nếu dùng kỹ thuật cấp phát động thì phải quản lý việc cấp thêm bộ nhớ khi chuỗi dãn ra (chẳng hạn do ghép chuỗi) và phải hủy bộ nhớ (khi không dùng nữa) để tránh việc cạn kiệt bộ nhớ của máy tính trong trường hợp có nhiều chương trình hoạt động đồng thời.

Tuy nhiên, với C++, ta hoàn toàn có thể khắc phục những khó khăn nêu trên trong các thao tác xử lý chuỗi.





**Kiểu chuỗi string trong thư viện STL của C++**



Thư viện chuẩn STL (Standard Template Library) cung cấp kiểu `string` (xâu ký tự), giúp các bạn tránh khỏi hoàn toàn các phiền phức nêu trên.Các chỉ thị `#include` cần khai báo để sử dụng string:

```
#include <string>
using std::string;
//using namespace std;
```

Nếu bạn muốn tận dụng các hàm của C-String, cần chuyển đổi giữa 2 kiểu dữ liệu này:



- Chuyển từ `string` sang C-String:

  ```
  string s;
  s.c_str();
  ```

- Chuyển từ C-String sang `string`:

  ```
  char* s_old = "ABC";
  string s(s_old);
  ```

* Kiểu String cũng có thể duyệt như mảng trong c++

  ```
  #include<iostream>
  using namespace std;
  int main()
  {
      string s = "ToanND-KX-1999";
      for(int i=0;i<s.size();i++)
          cout<<s[i]<<" ";
  }
  
  output: T o a n N D - K X - 1 9 9 9
  ```

  

**Các phương pháp, phép toán tiện ích của kiểu String**

Kiểu `string` của STL hỗ trợ các nhóm phương thức và phép toán tiện ích sau đây.



**Các phép toán và phương thức cơ bản**



- Các toán tử `+`, `+=` dùng để ghép hai chuỗi và cũng để ghép một ký tự vào chuỗi;

- Các phép so sánh theo thứ tự từ điển: `==` (bằng nhau), `!=` (khác nhau), `>` (lớn hơn), `>=` (lớn hơn hay bằng), `<` (nhỏ hơn), `<=` (nhỏ hơn hay bằng);

- Hàm `length()` và phép lấy chỉ số `[]` để duyệt từng ký tự của chuỗi: nếu `s` là biến kiểu `string` thì `s[i]` là ký tự thứ `i` của `s` với 0≤i<s.length()0≤i<s.length();

- Phép gán `=` dùng để gán biến kiểu `string` bằng một chuỗi, hoặc bằng `string` khác, chẳng hạn: `string s="ABCDEF"`; hay `s1=s2`; mà không cần copy xâu.

- Những constructor thường sử dụng nhất:

  ```
  string();
  string(const char *str);    // char* là kiểu dữ liệu xâu của C
  string(const string & str);
  ```

- Có thể dùng toán tử `<<` với `cout` để xuất một chuỗi ra màn hình hoặc dùng toán tử `>>` với `cin` để nhập một chuỗi ký tự đến khi gặp một khoảng trống thì dừng.

  ```
  char st[]="ABCDEF";
  string s;
  s="XYZ";
  cout << s << endl;
  s=st;
  cout << s.length() << " : " << s << endl;
  ```

- Một vấn đề thường nảy sinh trong các ứng dụng có sử dụng C-string: một C-String chưa khởi tạo cần được gán NULL. Tuy nhiên, rất nhiều hàm thư viện của C-String sẽ gặp sự cố trong thời gian chạy khi gặp đối tượng C-String là NULL. Chẳng hạn, lệnh

  ```
  char* x = NULL;
  cout << strlen(x);
  ```

  được một số trình biên dịch chấp nhận, nhưng với nhiều hiện thực khác của thư viện C-String, thì gặp lỗi trong thời gian chạy. string không gặp vấn đề này, ta hoàn toàn có thể cho 1 xâu là rỗng mà không gặp bất cứ lỗi nào: string s="";

String thực chất là một `vector<char>` có bổ sung thêm một số hàm và thuộc tính, do đó, nó có toàn bộ các tính chất của 1 vector, như hàm `size()`, `push_back()`, toán tử `[]`, …

- Các hàm từ

   

  ```
  vector
  ```

  :

  - `v.size()`: Số lượng phần tử
  - `v.empty()`: Trả về 1 nếu chuỗi rỗng, 0 nếu ngược lại.
  - `v.max_size()`: Trả về số lượng phần tử tối đa đã được cấp phát
  - `v1 == v2`: Trả về 1 nếu hai chuỗi giống nhau
  - `v1 != v2`: Trả về 1 nếu hai chuỗi khác nhau
  - `v.begin()`: Trả về **iterator** đầu tiên của chuỗi
  - `v.end()`: Trả về iterator cuối cùng của chuỗi (trỏ vào sau kí tự cuối cùng)
  - `v.front()`: Trả về phần tử đầu tiên của chuỗi
  - `v.back()`: Trả về phần tử cuối cùng của chuỗi
  - `v1.swap(v2)`: Hoán đổi 2 chuỗi với nhau (giống việc hoán đổi giá trị của 2 biến)

  ```
  #include <iostream>
  #include <conio.h>
  #include <string>
  using namespace std;
  int main()
  {
      string s = "Hello string"; // Khai báo biến kiểu string
      cout << "Noi dung string: " << s << endl; // In nôi dung string ra màn hình
      cout << "Chieu dai cua string: " << s.size() << endl;
      // Chiều dài
      cout << "Ky tu 0: " << s[0] << endl; // In ký tự đầu tiên của xâu
      cout << "Ky tu 1: " << s[1] << endl; // In ký tự thứ 2
      cout << "Ky tu 2: " << s[2] << endl; // In ký tự thứ 3
      getchar();
      return 0;
  }
  ```

- Nhập một `string` trên 1 dòng (chú ý `cin` sẽ chỉ đọc đến dấu cách hoặc xuống dòng đầu tiên): `istream& getline ( istream& in, string& str, char delimiter = ‘\n’);`

  Đọc 1 dòng văn bản từ `istream in` (có thể là file hay đối tượng chuẩn cin) từng ký tự đến khi ký tự delimiter được nhập vào (mặc định là `\n`)

  ```
  // getline with strings
  #include <iostream>
  #include <string>
  using namespace std;
  int main ()
  {
      string str;
      short age;
      cout << "Please enter full name and age"<< endl;
      getline( cin, str) >> age;
      cout << "Thank you " << str << "!\n";
      return 0;
  }
  
  ```

**Các phương thức chèn, xóa, lấy chuỗi con**



- Phương thức `substr(int pos, int nchar)` trích ra chuỗi con của một chuỗi cho trước, ví dụ `str.substr(2,4)` trả về chuỗi con gồm 4 ký tự của chuỗi `str` kể từ ký tự ở vị trí thứ 2 (ký tự đầu tiên của chuỗi ở vị trí 0).

  ```
  //get substring
  #include <iostream>
  #include <string>
  #include <conio.h>
  using namespace std;
  int main ()
  {
      string s="ConCho chay qua rao";
      cout << s.substr(2,4) << endl;
      // cout << new string(str.begin()+2, str.begin()+2+4);
      getchar();
      return 0;
  }
  ```

- Phương thức

   

  ```
  insert()
  ```

   

  chèn thêm ký tự hay chuỗi vào một vị trí nào đó của chuỗi

   

  ```
  str
  ```

   

  cho trước. Có nhiều cách dùng phương thức này:

  - `str.insert(int pos, char* s)`; chèn `s` (mảng ký tự kết thúc `\0`) vào vị trí `pos` của `str`;
  - `str.insert(int pos, string s)`; chèn chuỗi `s` (kiểu `string`) vào vị trí `pos` của chuỗi `str`;
  - `str.insert(int pos, int n, int ch)`; chèn `n` lần ký tự `ch` vào vị trí `pos` của chuỗi `str`;

  ```
  // inserting into a string
  #include <iostream>
  #include <string>
  #include <conio.h>
  using namespace std;
  int main ()
  {
      string str="day la .. xau thu";
      string istr = "them";
      str.insert(8, istr);
      cout << str << endl;
      getchar();
      return 0;
  }
  ```

- Phương thức `str.erase(int pos, int n)` xóa `n` ký tự của chuỗi `str` kể từ vị trí `pos`; nếu không quy định giá trị `n` thì tất cả các ký tự của `str` từ vị trí `pos` trở đi sẽ bị xóa

  ```
  // erase from a string
  #include <iostream>
  #include <string>
  #include <conio.h>
  using namespace std;
  int main ()
  {
      string str="day cung la xau thu";
      str.erase(0, 3); // " cung la xau thu"
      cout << str << endl;
      str.erase(6, 2);
      cout << str << endl; // " cung xau thu"
      getchar();
      return 0;
  }
  ```

## 



**So sánh**



Bạn có thể đơn giản là sử dụng những toán tử quan hệ (`==`, `!=`, `<`, `<=`, `>=`) được định nghĩa sẵn. Tuy nhiên, nếu muốn so sánh một phần của một chuỗi thì sẽ cần sử dụng phương thức `compare()`:



```
int compare ( const string& str ) const;
int compare ( const char* s ) const;
int compare ( size_t pos1, size_t n1, const string& str ) const;
int compare ( size_t pos1, size_t n1, const char* s) const;
int compare ( size_t pos1, size_t n1, const string& str, size_t pos2, size_t n2 ) const;
int compare ( size_t pos1, size_t n1, const char* s, size_t n2) const;
```



Hàm trả về 0 khi hai chuỗi bằng nhau và lớn hơn hoặc nhỏ hơn 0 cho trường hợp khác Ví dụ:



```
// comparing apples with apples
#include <iostream>
#include <string>
using namespace std;
int main ()
{
    string str1 ("green apple");
    string str2 ("red apple");
    if (str1.compare(str2) != 0)
    cout << str1 << " is not " << str2 << "\n";
    if (str1.compare(6,5,"apple") == 0)
    cout << "still, " << str1 << " is an apple\n";
    if (str2.compare(str2.size()-5,5,"apple") == 0)
    cout << "and " << str2 << " is also an apple\n";
    if (str1.compare(6,5,str2,4,5) == 0)
    cout << "therefore, both are apples\n";
    return 0;
}
```

## 



**Các phương pháp tính toán và thay thế**



- Phương thức `find()` tìm kiếm xem một ký tự hay một chuỗi nào đó có xuất hiện trong một chuỗi `str` cho trước hay không. Có nhiều cách dùng phương thức này:

  ```
  str.find(int ch, int pos = 0); tìm ký tự ch kể từ vị trí pos đến cuối chuỗi str
  str.find(char *s, int pos = 0); tìm s (mảng ký tự kết thúc ‘\0’) kể từ vị trí pos đến cuối
  str.find(string& s, int pos = 0); tìm chuỗi s kể từ vị trí pos đến cuối chuỗi.
  ```

  Nếu không quy định giá trị pos thì hiểu mặc nhiên là 0; nếu tìm có thì phương thức trả về vị trí xuất hiện đầu tiên, ngược lại trả về giá trị -1.

  ```
  //find substring
  #include <iostream>
  #include <string>
  #include <conio.h>
  using namespace std;
  int main ()
  {
      string str="ConCho chay qua rao";
      cout << str.find("chay") << endl; // 7
      cout << (int)str.find("Chay") << endl; // -1
      getchar();
      return 0;
  }
  ```

- Hàm tìm kiếm ngược (`rfind`)

  ```
  //find from back
  #include <iostream>
  #include <string>
  #include <conio.h>
  using namespace std;
  int main ()
  {
      string str="ConCho chay qua chay qua rao";
      cout << str.find("chay") << endl; // 7
      cout << (int)str.rfind("chay") << endl; // 16
      getchar();
      return 0;
  }
  ```

- Phương thức `replace()` thay thế một đoạn con trong chuỗi `str` cho trước (đoạn con kể từ một vị trí `pos` và đếm tới `nchar` ký tự ký tự về phía cuối chuỗi) bởi một chuỗi `s` nào đó, hoặc bởi `n` ký tự `ch` nào đó. Có nhiều cách dùng, thứ tự tham số như sau:

  ```
  str.replace(int pos, int nchar, char *s);
  str.replace(int pos, int nchar, string s);
  str.replace(int pos, int nchar, int n, int ch);
  
  string str="con cho la con cho con. Con meo ko phai la con cho";
  str.replace(4, 3, "CHO"); // "con CHO la con cho con. Con meo ko phai la con cho";
  cout << str << endl;
  getchar();
  ```



**Tách xâu**

Trong việc xử lý xâu ký tự, không thể thiếu được các thao tác tách xâu ký tự thành nhiều xâu ký tự con thông qua các ký tự ngăn cách. Các hàm này có sẵn trong các ngôn ngữ khác như Visual Basic, Java, hay thậm chí là trong `<string.h>`. Với STL, các bạn có thể dễ dàng làm điều này với `stringstream`:



```
string S = "Xin chao tat ca cac ban"; // Khởi tạo giá trị của xâu
stringstream ss(S); // Khởi tạo stringstream từ xâu S

while (ss >> token) { // Đọc lần lượt các phần của xâu. Các phần tách nhau bởi dấu cách hoặc xuống dòng.
  cout << token << endl;
}
```

Output:

```
Xin
chao
tat
ca
cac
ban
```



Chú ý rằng, cách này cũng có thể dễ áp dụng nếu bạn muốn chuyển số thành xâu (hoặc ngược lại), tách 1 xâu thành nhiều số.

Nếu không muốn sử dụng `stringstream`, các bạn cũng có thể tự xây dựng hàm tách xâu như sau:

```
string S = "Xin chao tat ca cac ban"; // Khởi tạo giá trị của xâu
string::iterator t, t2; // Các biến lặp
vector<string> split; // Mảng các xâu (lưu kết quả tách)

for (t=S.begin(); t<S.end();)
{
    // Lặp từ vị trí bắt đầu
    t2=find(t, S.end(), ' '); // TÌm ký tự space ' ' đầu tiên
    // kể từ vị trí t
    if (t!=t2) split.push_back(string(t, t2)); // Lấy xâu ký tự giữa 2 vị trí
    t = t2+1; // Chuyển sang vị trí sau
}
for (int i=0; i<splitìsize(); i++)
cout << split[i] << endl; // In mảng các xâu ký tự
getchar();
```

Output:

```
Xin
chao
tat
ca
cac
ban
```

Đoạn chương tr.nh sử dụng các kỹ thuật sau

- Phương thức `find(vị_trí_đầu, vị_trí_cuối, ký_tự_tìm)` dùng để tìm vị trí đầu tiên của `ký_tự_tìm` bắt đầu từ `vị_trí_đầu`. Hàm này trả về vị trí của ký tự tìm được (nếu tìm thấy) hoặc `vị_trí_cuối` (nếu không tìm thấy)
- `string` có thể khởi tạo từ một đoạn ký tự con của một xâu ký tự khác với cú pháp `string(vị_trí_đầu, vị_trí_cuối)`
- Đoạn chương trình thực hiện tách các xâu ký tự kể cả trong trường hợp có nhiều ký tự `space` nằm liên tiếp nhau. Một cách đơn giản hơn là bạn có thể gọi hàm `strtok()` trong `string.h` để làm việc này, nhưng không may là hàm này thao tác trên `char*` chứ không phải `string`. Hàm thành viên `c_str()` sẽ giúp bạn chuyển từ `string` thành dạng `const charT* c_str () const`;

Hàm này cũng tự động sinh ra ký tự null chèn vào cuối xâu.

Từ prototype ta cũng thấy được hàm trả về một hằng chuỗi, điều này đồng nghĩa với việc ta không thể thay đổi chuỗi trả về. Gọi phương thức c_str();

```
string s = "some_string";
cout << s.c_str() << endl;
cout << strlen(s.c_str()) << endl;
```

Sau đây là ví dụ bên trên được viết lại dùng hàm thành viên `c_str()` và các hàm trong `<string.h>`

```
// strings vs c-strings
#include <iostream>
#include <string.h>
#include <string>
using std::string;
int main ()
{
    char* cstr;
    char* p;
    string str ("Xin chao tat ca cac ban");
    cstr = new char [str.size()+1];
    strcpy (cstr, str.c_str());
    // cstr là 1 bản sao c-string của str
    p=strtok (cstr," ");
    while (p!=NULL)
    {
        cout << p << endl;
        p=strtok(NULL," ");
    }
    delete[] cstr;
    return 0;
}
```

Output:

```
Xin
chao
tat
ca
cac
ban
```

## 

**Chuyển đổi hàng loạt với transform**

```
OutputIterator transform( InputIterator first,
InputIterator last,
OutputIterator result,
UnaryOperation unary_op );

#include <cctype> // for toupper
#include <string>
#include <algorithm> //for transform
using namespace std;
char alphabet(char c)
{
    static char ch = 'a';
    return ch++;
}
int main()
{
    string s("this is a lower case string");
    transform(s.begin(), s.end(), s.begin(), toupper);
    cout << s << endl;
    transform(s.begin(), s.end(), s.begin(), alphabet);
    cout << s;
    return 0;
}
```

## 





**Một số phương thức khác**

Còn nhiều phương thức tiện ích khác như: `append()`, `rfind()`, `find_first_not_of()`, `find_last_not_of()`, `swap()`. Cách dùng các hàm này đều được trình bày trong hệ thống hướng dẫn (help) của các môi trường có hỗ trợ STL (trong VC++ là MSDN). Ngoài ra các phương thức như `find_first_of()` tương tự như `find()`, `find_last_of()` tương tự như `rfind()`



# 5. Function (Hàm)



Định nghĩa của hàm:

```c++
type name ( argument1, argument2, ...) {
  statement
}
```



Trong đó:

*  `type`  là kiểu dữ liệu trả về của hàm
*  `name` là tên gọi của hàm: lưu ý tên hàm không được trùng với các từ khóa đã được quy định trong C++
*  `arguments` là các tham số truyền vào, với số lượng không hạn chế số lượng cũng như kiểu dữ liệu

*  `statement` là thân của hàm. Hàm có thể một lệnh hoặc nhiều lệnh kết hợp







**Ví dụ 1:**

```c++
#include <iostream>
using namespace std;
int addition (int a, int b)
{
    return a+b;
}

int main ()
{
  int z;
  z = addition (5,3);
  cout << "The result is " << z;
  return 0;
}

output:  The result is 8
```





**Ví dụ 2:**

```c++
#include<iostream>
#include<string>
using namespace std;
string add(string a, string b)
{
    return a+b;
}
int main()
{
    string a = "Toan";
    string b = "KX";
    string c = add(a,b);
    cout<<c;
    reuturn 0;
}
output: ToanKX
```





**Hàm void(): hàm không kiểu**

* Là hàm không có câu lệnh return: Hàm này thường được dùng để hiển thị, hoặc cập nhật các giá trị trong CP

  Lưu ý: Làm chỉ dùng để hiển thị hoặc cập nhật không nên sử dụng để tính toán trong hàm void



```c++
#include<iostream>
using namespace std;

void my_function()
{
  cout << "I'm a function!";
}

int main ()
{
  my_function ();
  return 0;
}
output:  I'm a function!
```





**Hàm - Tham số giá trị và tham số biến trong C++**

Mục đích của hàm này là có thể sử dụng để cập nhật giá trị các biến, xem qua 2 ví dụ dưới đây



```c++
#include <iostream>
using namespace std;
void duplicate (int a, int b, int c)
{
  a*=2;
  b*=2;
  c*=2;
}

int main ()
{
  int x=1, y=3, z=7;
  duplicate (x, y, z);
  cout << "x=" << x << ", y=" << y << ", z=" << z;
  return 0;
}

output: x=1, y=3, z=7
```





Như chúng ta thấy hàm khi không truyền tham trị & thì các giá trị x,y,z không thay đổi



```c++
#include <iostream>
using namespace std;
void duplicate (int &a, int &b, int &c)
{
  a*=2;
  b*=2;
  c*=2;
}

int main ()
{
  int x=1, y=3, z=7;
  duplicate (x, y, z);
  cout << "x=" << x << ", y=" << y << ", z=" << z;
  return 0;
}
output:  x=2, y=6, z=14
```



Tóm lại khi dùng tham trị & sẽ cập nhật giá trị của biến sau khi chạy qua hàm, nếu không dùng & sẽ không cập nhật mà chỉ tính toán



**Hàm - Giá trị mặc định của tham số trong C++**



Khi định nghĩa một hàm chúng ta có thể chỉ định những giá trị mặc định sẽ được truyền cho các đối số trong trường hợp chúng bị bỏ qua khi hàm được gọi. Để làm việc này đơn giản chỉ cần gán một giá trị cho đối số khi khai báo hàm. Nếu giá trị của tham số đó vẫn được chỉ định khi gọi hàm thì giá trị mặc định sẽ bị bỏ qua.



```c++
// default values in functions
#include <iostream>
using namespace std;
int divide (int a, int b=2)
{
  int r;
  r=a/b;
  return (r);
}
 
int main ()
{
  cout << divide (12); // divide(12,2)
  cout << endl;
  cout << divide (20,4);// divide(20,4)
  return 0;
}
output: 6
        5
```





**Các hàm trong thư viện hay sử dụng trong tính toán**



* ``max(a,b)`` trả về giá trị lớn nhất của 2 biến:

  a = 4, b = 5 => max(a,b) = 5

* `min(a,b)` trả về giá trị nhỏ nhất của 2 biến

  a = 4, b = 5 => min(a,b) = 4

* `swap(a,b)` hàm đổi chỗ giá trị của 2 biến

  a = 4, b = 5 => swap(a,b) => a = 5, b=4

* `pow(a,b)` hàm tính lũy thừa với a là cơ số, b là số lũy thừa

  a = 4, b = 5 => pow(a,b) = 4^5

* `sqrt(x)` hàm tính toán căn bậc 2

  a = 9 =>  sqrt(a) = 3

Ngoài ra còn có các hàm tính toán có thể gặp trong CP các bạn có thể tham khảo tại link dưới đây



- [Hàm acos() trong C / C++](https://freetuts.net/ref/ham-acos-trong-c++-433.html)
- [Hàm asin() trong C / C++](https://freetuts.net/ref/ham-asin-trong-c++-434.html)
- [Hàm atan() trong C / C++](https://freetuts.net/ref/ham-atan-trong-c++-435.html)
- [Hàm cbrt() trong C / C++](https://freetuts.net/ref/ham-cbrt-trong-c++-437.html)
- [Hàm ceil() trong C / C++](https://freetuts.net/ref/ham-ceil-trong-c++-438.html)
- [Hàm abs() trong C / C++](https://freetuts.net/ref/ham-abs-trong-c++-439.html)
- [Hàm cos() trong C / C++](https://freetuts.net/ref/ham-cos-trong-c++-440.html)
- [Hàm exp() trong C / C++](https://freetuts.net/ref/ham-exp-trong-c-c++-441.html)
- [Hàm fmax() và fmin() trong C / C++](https://freetuts.net/ref/ham-fmax-va-fmin-trong-c-c++-442.html)
- [Hàm log() trong C / C++](https://freetuts.net/ref/ham-log-trong-c-c++-443.html)
- [Hàm pow() trong C / C++](https://freetuts.net/ref/ham-pow-trong-c-c++-444.html)
- [Hàm round() trong C / C++](https://freetuts.net/ref/ham-round-trong-c-c++-445.html)
- [Hàm sqrt() trong C / C++](https://freetuts.net/ref/ham-sqrt-trong-c-c++-446.html)
- [Hàm sin() trong C / C++](https://freetuts.net/ref/ham-sin-trong-c-c++-447.html)



Một số tài liệu tham khảo:

https://www.cplusplus.com/doc/tutorial/functions

https://www.tutorialspoint.com/cplusplus/cpp_functions.htm







# Kiểu dữ liệu do người dùng tự định nghĩa trong C++







##### Tự định nghĩa các kiểu dữ liệu (typedef)

C++ cho phép chúng ta định nghĩa các kiểu dữ liệu của riêng mình dựa trên các kiểu dữ liệu đã có. Để có thể làm việc đó chúng ta sẽ sử dụng từ khoá `typedef`, dạng thức như sau:

`typedef existing_type new_type_name;`

Trong đó: `existing_type` là một kiểu dữ liệu đã được định nghĩa và `new_type_name` là tên của kiểu dữ liệu mới



ví dụ:

```c++
typedef string S;
typedef pair<int,int> pii;
typedef char C;
typedef unsigned int WORD;
typedef char * string_t;
typedef char field [50];
```

sau khi định nghĩa ta hoàn toàn có thể sử dụng chúng một cách hợp lệ



```c++
S s;
pii p;
C achar, anotherchar, *ptchar1;
WORD myword;
string_t ptchar2;
field name;
```



**Union**

Union cho phép một phần bộ nhớ có thể được truy xuất dưới dạng nhiều kiểu dữ liệu khác nhau mặc dù tất cả chúng đều nằm cùng một vị trí trong bộ nhớ. Phần khai báo và sử dụng nó tương tự với cấu trúc nhưng chức năng thì khác hoàn toàn:



```c++
union model_name {
  type1 element1;
  type2 element2;
  type3 element3;
  .
  .
} object_name;
```

Tất cả các phần tử của union đều chiếm cùng một chỗ trong bộ nhớ. Kích thước của nó là kích thước của phần tử lớn nhất. Ví dụ:

```c++
union mytypes_t {
  char c;
  int i;
  float f;
} mytypes;
```



Định nghĩa 3 phần tử

```c++
mytypes.c
mytypes.i
mytypes.f
```

mỗi phần tử có một kiểu dữ liệu khác nhau. Nhưng vì tất cả chúng đều nằm cùng một chỗ trong bộ nhớ nên bất kì sự thay đổi nào đối với một phần tử sẽ ảnh hưởng tới tất cả các thành phần còn lại.





**Struct**

```c++
Cú pháp:

struct <structure_name > {
    <data_type member_name_1>;
    <data_type member_name_i>;
    ...
    } <structure_variable1>,<structure_variable2>,...;
```



Trong đó:

 `structure_name : Tên cấu trúc`

`data_type member_name_i :  data_type là kiểu dữ liệu của các thành phần trực thuộc structure. `

`structure_variable: Tên biến cấu trúc`





**Ví dụ 1:**

```c++
#include<iostream>
using namespace std;
struct toado
{
    int x = 5;
    int y = 10;
}a;
int main()
{
    cout<<"x:"<<a.x<<endl;
    cout<<"y:"<<a.y<<endl;
}

```





**Bài tập áp dụng**



![image](https://user-images.githubusercontent.com/42260182/129468709-f43403df-3c00-438b-9c83-dcdebee1685a.png)





+ Phân tích: 

  Bài này là bài tiêu biểu sử dụng giải thuật tham lam nhưng mình sẽ giới thiệu ở đây bằng phương pháp áp dụng struct để giải

  Tham lam ở đây chính là ta sắp xếp 2 dãy theo chiều tăng dần của công việc kết thúc và chỉ cần kiếm tra xem công việc đó thời gian bắt đầu có nhỏ hơn thời gian kết thúc hay không.

  + Nếu thời gian bắt đầu lớn hơn hoặc bằng thời gian kết thúc của người trước đó thì ta tăng tăng thêm được 1 phương án và cập nhật lại
  + Nếu ngược lại thì ta xét tiếp người bắt đầu ở vị trí tiếp theo





Do phần này là phần C++ cơ bản nên mình sẽ không đi sâu vào phân tích thuật toán mà chỉ giới thiệu cách giải quyết áp dụng struct nên nếu thấy khó hiểu thì các bạn có thể xem lại phần phân tích chi tiết ở các chương giải thuật tiếp theo.



```c++
#include<bits/stdc++.h>
using namespace std;
int n;
struct data
{
    int fi, se;
};
data h[1005];
bool cmp(data a, data b)
{
    return a.se < b.se;
}
int main()
{
    ios_base::sync_with_stdio(0);
    int t;
    cin>>t;
    while(t--)
    {
        cin>>n;
        for(int i=0;i<n;i++)
            cin>>h[i].fi;
        for(int i=0;i<n;i++)
            cin>>h[i].se;

        sort(h,h+n,cmp);
        int ans=1, i=0;
        for(int j=1;j<n;j++)
        {
            if(h[j].fi >= h[i].se)
            {
                ans++;
                i=j;
            }
        }
        cout<<ans<<endl;
    }
}
```



Ngoài ra bài này còn có thể sử dụng kiểu cấu trúc pair mình sẽ giới thiệu ở phần các cấu trúc nâng cao.





update....





# STACK, QUEUE



Giới thiệu: 

Stack, Queue là các cấu trúc dữ liệu hay dùng và thường gặp trong các bài toán, chúng ta có thể xây dựng stack, queue bằng Linklist hoặc có thể cài đặt bằng mảng 1 chiều. Nhưng trong bài này mình sẽ hướng dẫn các bạn áp dụng thư viện stack, queue trong giải thuật

**1. Stack**

Stack là cấu trúc ngăn xếp, cấu trúc là FIFO (First in first out) có nghĩa là vào trước ra trước, các bạn có thể hình dung stack như một đống sách xếp chồng lên nhau. Việc thêm một phần tử vào stack cũng như đặt một cuốn sách lên đỉnh đống sách, việc lấy một phần tử trong stack ta cũng hình dung là lấy cuốn sách đầu tiên của đống sách đó ra.

![image](https://user-images.githubusercontent.com/42260182/129472175-56830959-e8fe-4b14-9ce4-efcbf273cd45.png)





**2. Queue**

Queue là cấu trúc hàng đợi dạng FILO (first in last out) vào trước ra sau, các bạn có thể hình dung queue như một đống sách nằm ngang. Khi thêm một phần tử vào queue thì ta đẩy một cuốn sách vào từ bên trái. Khi lấy một phần tử thì nó sẽ là cuốn sách ở đầu bên còn lại







​                           ![image](https://user-images.githubusercontent.com/42260182/129472258-a4fa15a2-267c-4d06-9e11-a1a6c73665eb.png) 







Cú pháp trong stack

```c++
#include<iostream>
#include<stack>
using namespace std;
int main()
{
    stack<int> st; // Khai báo stack với các kiểu trả về có thể là int, long, long long, char, string....
    cout<<st.size()<<endl;; //Trả về số lượng phần tử trong stack
    st.push(1); // Thêm một phần tử vào đầu stack
    cout<<st.top()<<endl;;// in ra phần tử đầu stack
    st.pop(); // xóa phần tử trong stack
}
```



**Bài tập áp dụng**

![image](https://user-images.githubusercontent.com/42260182/129473239-17eaed3e-04f6-4c33-b763-35475320f2d0.png)





Hướng dẫn: áp dụng cấu trúc dữ liệu stack đẩy toàn bộ các kí tự trong string vào ngăn xếp khi đó ta chỉ cần lấy ra lần lượt các phần tử của stack ta được output như đề bài



```c++
#include<iostream>
#include<stack>
using namespace std;
int main()
{
    stack<char> st;
    string s;
    cin>>s;

    for(int i=0;i<s.size();i++)
        st.push(s[i]);

    while(!st.empty())  //Kiểm tra stack có rỗng hay không
    {
        cout<<st.top();
        st.pop();
    }
}

```



![image](https://user-images.githubusercontent.com/42260182/129473456-079d1c25-1f86-4c6a-b6f5-c89240298c8e.png)





Phân tích: 

Để chuyển một số nguyên dương thành số nhị phân ta làm như sau:

Trong khi `n > 0` thì ta lấy `n` chia cho `2` và lưu số dư của phép chia đó lại. Cứ làm vậy đến khi nào `n = 0` thì dừng lại.

Kết quả cần tìm chính là danh sách các số dư được đọc ngược lại, ta sẽ nghĩ ngay đến việc sùng **stack** để lưu các số dư này, sau đó chỉ cần in ra **stack** là được.





```c++
#include<iostream>
#include<stack>

using namespace std;

int main(){
	stack<char> st;
	int n;
	cin >> n;
    while(n > 0){
		st.push(n%2+'0');
		n /= 2;
	}
	while(!st.empty()){
		cout << st.top();
		st.pop();
	}
    return 0;
}
```



Chúng ta sẽ đi sâu hơn ở các bài chuyên giải thuật về stack ở phần sau.





Cú pháp trong queue 

```c++
#include<iostream>
#include<queue>
using namespace std;
int main()
{
    queue<int> q; //Khai báo queue, các kiểu trả về có thể là int, long, long long, float, char, string...
    cout<<q.size()<<endl;// in ra số lượng phần tử có trong hàng đợi
    q.push(1);//thêm phần tử 1 vào hàng đợi
    q.push(2);//thêm phần tử 2 vào hàng đợi
    q.push(3);//thêm phần tử 2 vào hàng đợi

    // các bạn có thể hình dung queue hiện tại  3 2 1
    cout<<q.front()<<endl;  //in ra phần tử đầu ra của queue

    q.pop(); //bỏ đi phần tử đầu ra của queue

    //in ra toàn bộ các phần tử trong queue còn lại

    while(!q.empty())
    {
        cout<<q.front()<<" ";
        q.pop();
    }
}
```



![image](https://user-images.githubusercontent.com/42260182/129473599-5d134df1-b915-443f-b46b-f31c147237c3.png)



Cách làm: Áp dụng cấu trúc dữ liệu queue

Đầu tiên ta đẩy toàn bộ input vào queue. Với k lần biến đổi ta thực hiện k bước, mỗi bước ta lấy phần tử phía bên phải của hàng đợi (hình dung quyển sách nằm ngang)  loại bỏ phần tử đó và push lại, khi đó phần tử bên phải nhất của hàng sách sẽ là phần tử bên trái đầu tiên của hàng sách mới cứ tiếp tục như vậy cho đến k lần rồi in toàn bộ các phần tử trong queue



```c++
#include<iostream>
#include<queue>

using namespace std;

int main(){
    queue<int> q;
    int n, k, temp;
    cin >> n;
    for (int i = 0; i < n; i++){
    	cin >> temp;
    	q.push(temp);
	}
	cin >> k;
    for (int i = 0; i < k; i++){
        int x = q.front();
        q.pop();
        q.push(x);
    }
    while (!q.empty()){
        cout << q.front() << " ";
        q.pop();
    }
    
    return 0;
}
```







**PIORITY QUEUE**



Mình sẽ giới thiệu thêm 1 cấu trúc nâng cao về priority queue. Cấu trúc này được xây dựng từ cấu trúc dữ liệu vun đống 'heap' nhưng dùng để xây dựng hàng đợi ưu tiên giúp ta có thể lấy ra phần tử nhỏ nhất/ lớn nhất của một dãy số chỉ với độ phức tạp O(log(n)) 



```c++
#include <iostream>
#include <queue>

using namespace std;

void showpq(priority_queue<int> gq)
{
    priority_queue<int> g = gq;
    while (!g.empty()) {
        cout<< g.top()<<" ";
        g.pop();
    }
    cout << '\n';
}

int main()
{
    priority_queue<int> pq;
    pq.push(10);
    pq.push(30);
    pq.push(20);
    pq.push(5);
    pq.push(1);

    cout << "Hien thi priority queue: ";
    showpq(pq);

    cout << "pq.size() : " << pq.size()<<endl;
    cout << "pq.top() : " << pq.top()<<endl;

    cout << "pq.pop() : ";
    pq.pop();
    showpq(pq);

    return 0;
}


output:

Hien thi priority queue: 30 20 10 5 1
pq.size() : 5
pq.top() : 30
pq.pop() : 20 10 5 1
```



Nếu muốn tạo ra hàng đợi ưu tiên với phần tử đầu tiên là nhỏ nhất ta làm như sau:

```c++
#include <iostream>
#include <queue>

using namespace std;

void showpq(
    priority_queue<int, vector<int>, greater<int> > gq)
{
    priority_queue<int, vector<int>,
                                greater<int> > g = gq;
    while (!g.empty()) {
        cout << g.top()<<" ";
        g.pop();
    }
    cout << '\n';
}

int main()
{
    priority_queue<int, vector<int>,
                       greater<int> > pq;
    pq.push(10);
    pq.push(30);
    pq.push(20);
    pq.push(5);
    pq.push(1);

    cout << "Hien thi priority queue: ";
    showpq(pq);

    cout << "pq.size() : " << pq.size()<<endl;
    cout << "pq.top() : " << pq.top()<<endl;

    cout << "pq.pop() : ";
    pq.pop();
    showpq(pq);

    return 0;
}


output:

Hien thi priority queue: 1 5 10 20 30
pq.size() : 5
pq.top() : 1
pq.pop() : 5 10 20 30
```



update...

# CÁC CẤU TRÚC DỮ LIỆU NÂNG CAO







Mình xin giới thiệu đến các bạn các cấu trúc dữ liệu nâng cao thường sử dụng trong lập trình thi đấu. Các phần mình trình bày dưới đây đều được sử dụng trong bộ thư viên STL của C++. Nếu bạn nào có nhu cầu tìm hiểu chi tiết để xây dựng từng cấu trúc thì rất tốt nhưng đó sẽ tốn rất nhiều thời gian của các bạn vì đơn giản Việc sử dụng thành thạo STL sẽ là rất quan trọng nếu các bạn có ý định tham gia các kì thi như Olympic Tin Học, hay ACM. “STL sẽ nối dài khả năng lập trình của các bạn” (trích lời thầy Lê Minh Hoàng)





**VECTOR (Mảng động)**

vector là một cấu trúc nâng cao của mảng nên nó sẽ có ưu điểm là linh hoạt hơn nhiều so với mảng và 1 số điểm nổi trội sau đây

- Bạn không cần phải khai báo kích thước của mảng ví dụ int A[100]..., vector có thể tự động nâng kíck thước lên.
- Nếu bạn thêm 1 phần tử vào vector đã đầy rồi, thì vector sẽ tự động tăng kíck thước của nó lên để dành chỗ cho giá trị mới này.- Vector còn có thể cho bạn biết số lượng các phần tử mà bạn đang lưu trong nó.
- Dùng số phần tử âm vẫn được trong vector ví dụ A-10], A[-3], rất tiện trong việc cài đặt các giải thuật khác.



Ví dụ

```c++
#include <vector>
...
/* Vector 1 chiều */
/* tạo vector rỗng kiểu dữ liệu int */
vector <int> first;
//tạo vector với 4 phần tử là 100
vector <int> second (4,100);
// lấy từ đầu đến cuối vector second
vector <int> third (second.begin(),second.end())
//copy từ vector third
vector <int> four (third)
/*Vector 2 chiều*/
/* Tạo vector 2 chiều rỗng */
vector < vector <int> > v;
/* khai báo vector 5×10 */
vector < vector <int> > v (5, 10) ;
/* khai báo 5 vector 1 chiều rỗng */
vector < vector <int> > v (5) ;
//khai báo vector 5*10 với các phần tử khởi tạo giá trị là 1
vector < vector <int> > v (5, vector <int> (10,1) ) ; 

```

Các hàm thành viên:

* Capacity:
  *  size : trả về số lượng phần tử của vector. ĐPT O(1). 
  *  empty : trả về true(1) nếu vector rỗng, ngược lại là false(0). ĐPT O(1)
  *  operator [] : trả về giá trị phần tử thứ []. ĐPT O(1). 
  *  at : tương tự như trên. ĐPT O(1). 
  *  front: trả về giá trị phần tử đầu tiên. ĐPT O(1).
  *  back: trả về giá trị phần tử cuối cùng. ĐPT O(1). 
* Chỉnh sửa
  * push_back : thêm vào ở cuối vector. ĐPT O(1). 
  * pop_back : loại bỏ phần tử ở cuối vector. ĐPT O(1). 
  * insert (iterator,x): chèn “x” vào trước vị trí “iterator” ( x có thể là phần tử hay iterator của 1 đoạn phần tử…). ĐPT O(n). 
  * erase : xóa phần tử ở vị trí iterator. ĐPT O(n). 
  * swap : đổi 2 vector cho nhau (ví dụ: first.swap(second);). ĐPT O(1). - clear: xóa vector. ĐPT O(n). 
* Nhận xét
  * Sử dụng vector sẽ tốt khi: 
    *  Truy cập đến phần tử riêng lẻ thông qua vị trí của nó O(1) 
    *  Chèn hay xóa ở vị trí cuối cùng O(1). 
  * Vector làm việc giống như một “mảng động”. 

ví dụ

```c++
#include <iostream>
#include <vector>
using namespace std;
vector <int> v; //Khai báo vector
vector <int>::iterator it; //Khai báo iterator
vector <int>::reverse_iterator rit; //Khai báo iterator ngược
int i;
main() {
 for (i=1;i<=5;i++) v.push_back(i); // v={1,2,3,4,5}
 cout << v.front() << endl; // In ra 1
 cout << v.back() << endl; // In ra 5

 cout << v.size() << endl; // In ra 5

 v.push_back(9); // v={1,2,3,4,5,9}
 cout << v.size() << endl; // In ra 6

 v.clear(); // v={}
 cout << v.empty() << endl; // In ra 1 (vector rỗng)

 for (i=1;i<=5;i++) v.push_back(i); // v={1,2,3,4,5}
 v.pop_back(); // v={1,2,3,4}
 cout << v.size() << endl; // In ra 4

 v.erase(v.begin()+1); // Xóa ptử thứ 1 v={1,3,4}
 v.erase(v.begin(),v.begin()+2); // v={4}
 v.insert(v.begin(),100); // v={100,4}
 v.insert(v.end(),5); // v={100,4,5}

 /*Duyệt theo chỉ số phần tử*/
 for (i=0;i<v.size();i++) cout << v[i] << " "; // 100 4 5
 cout << endl; 
    
/*Chú ý: Không nên viết
 for (i=0;i<=v.size()-1;i++) ...
 Vì nếu vector v rỗng thì sẽ dẫn đến sai khi duyệt !!!
 */

 /*Duyệt theo iterator*/
 for (it=v.begin();it!=v.end();it++)
 cout << *it << " " ;
 //In ra giá trị ma iterator đang trỏ tới "100 4 5"
 cout << endl;
 /*Duyệt iterator ngược*/
 for (rit=v.rbegin();rit!=v.rend();rit++)
 cout << *rit << " "; // 5 4 100
 cout << endl;

 system("pause");
} 
```



![image](https://user-images.githubusercontent.com/42260182/129530470-1afe7f45-f5dd-4148-956e-86cea5d3fe4a.png)

```c++
#include<bits/stdc++.h>
using namespace std;
vector < vector <int> > a (10001);
int n,m,i,j,u,v;
int main()
{
    cin>>n>>m;
    for(int i=1;i<=m;i++)
    {
        cin>>u>>v;
        a[u].push_back(v);
        a[v].push_back(u);
    }
    for(int i=1;i<=m;i++)
    {
        sort(a[i].begin(), a[i].end());
    }
    for(int i=1;i<=m;i++)
    {
        for(int j=0;j<a[i].size();j++)
            cout<<a[i][j]<<" ";
        cout<<endl;
    }
}

```











### STL Iterator

Một Iterator là một đối tượng có thể đi qua (iterate over) một container class mà không cần biết trật tự các phần tử bên trong mảng. Iterator còn là một cách để truy cập dữ liệu bên trong các container.

Các bạn có thể hình dùng Iterator giống như một con trỏ trỏ đến một phần tử nào đó bên trong container với một số toán tử đã được định nghĩa:

- Operator* cereference và trả về giá trị bên trong container tại vị trí mà iterator được đặt.
- Operator++ di chuyển iterator đến phần tử tiếp theo trong container.
- Operator-- ngược lại so với operator++.
- Operator== và operator!= dùng để so sánh vị trí tương đối của 2 phần tử đang được trỏ đến bởi 2 iterator.
- Operator= dùng để gán vị trí mà iterator trỏ đến.

#### Khai báo một Iterator

Với mỗi container class chúng ta sẽ có một kiểu iterator tương ứng. Mình sẽ lấy ví dụ về iterator của class std::vector như sau:

```c++
#include <iostream>
#include <vector>
using namespace std;

int main()
{
	std::vector<int> vec;

	std::vector<int>::iterator iter;

	return 0;
}
```



```c++
/*khai báo iterator “it”*/
vector <int> :: iterator it;
/* trỏ đến vị trí phần tử đầu tiên của vector */
it=vector.begin();
/*trỏ đến vị trí kết thúc (không phải phần tử cuối cùng nhé) của vector) */
it=vector.end();
/* khai báo iterator ngược “rit” */
vector <int> :: reverse_iterator rit; rit = vector.rbegin();
/* trỏ đến vị trí kết thúc của vector theo chiều ngược (không phải phần tử
đầu tiên nhé*/
rit = vector.rend(); 

```







**SET (Tập hợp)**



Tập hợp mình nhớ không nhầm là các bạn đã được học môn toán lớp 6. Set là tập hợp trong đó các phần tử chỉ suất hiện tối đa 1 lần

Khai báo

```c++
#include <set>
set <int> s;
set <int, greater<int> > s; 
```



* Capacity:
  * size : trả về kích thước hiện tại của set. ĐPT O(1) 
  * true nếu set rỗng, và ngược lại. ĐPT O(1). 
* Modifiers:
  * insert : Chèn phần tử vào set. ĐPT O(logN). 
  * erase : có 2 kiểu xóa: xóa theo iterator, hoặc là xóa theo khóa. ĐPT O(logN). 
  * clear : xóa tất cả set. ĐPT O(n). 
  * swap : đổi 2 set cho nhau. ĐPT O(n). 
* Operations
  * find : trả về itarator trỏ đến phần tử cần tìm kiếm. Nếu không tìm thấy itarator trỏ về “end” của set. ĐPT O(logN).
  * lower_bound : trả về iterator đến vị trí phần tử bé nhất mà không bé hơn (lớn hơn hoặc bằng) khóa (dĩ nhiên là theo phép so sánh), nếu không tìm thấy trả về vị trí “end” của set. ĐPT O(logN).
  * upper_bound: trả về iterator đến vị trí phần tử bé nhất mà lớn hơn khóa, nếu không tìm thấy trả về vị trí “end” của set.. ĐPT O(logN).
  * count : trả về số lần xuất hiện của khóa trong container. Nhưng trong set, các phần tử chỉ xuất hiện một lần, nên hàm này có ý nghĩa là sẽ return 1 nếu khóa có trong container, và 0 nếu không có. ĐPT O(logN). 

Ví dụ:

```c++
#include<iostream>
#include<set>
int main()
{
    std::set<int> s;
    s.insert(1);
    s.insert(2);
    s.insert(3);
    s.insert(1);

    // Chỉ 3 phần tử được thêm vào "s"
    std::cout<<"Số lượng phần tử: "<<s.size()<<std::endl;
    return 0;
}

output: 
Số lượng phần tử: 3
    
```



ví dụ

```c++
#include <iostream>
#include <set>
using namespace std;
main() { 
    set <int> s;
    set <int> ::iterator it;
    s.insert(9); // s={9}
    s.insert(5); // s={5,9}
    cout << *s.begin() << endl; //In ra 5
    s.insert(1); // s={1,5,9}
    cout << *s.begin() << endl;
    
    it=s.find(5);
    if (it==s.end()) cout << "Khong co trong container" << endl;
    else cout << "Co trong container" << endl; 
    
    
    s.erase(it); // s={1,9}
    s.erase(1); // s={9}
    s.insert(3); // s={3,9}
    s.insert(4); // s={3,4,9}
    
    
    
    
    it=s.lower_bound(4);
    if (it==s.end()) cout << "Khong co phan tu nao trong set khong be hon 4" << endl;
    else cout << "Phan tu be nhat khong be hon 4 la " << *it << endl; // In ra 4

    it=s.lower_bound(10);
    if (it==s.end()) cout << "Khong co phan tu nao trong set khong be hon 10" << endl;
    else cout << "Phan tu be nhat khong be hon 10 la " << *it << endl; // Khong co ptu nao

    it=s.upper_bound(4);
    if (it==s.end()) cout << "Khong co phan tu nao trong set lon hon 4" << endl;
    else cout << "Phan tu be nhat lon hon 4 la " << *it << endl; // In ra 9
    
    
    
    /* Duyet set */
    for (it=s.begin();it!=s.end();it++) {
        cout << *it << " ";}
    // In ra 3 4 9
    
    cout << endl; 
    return 0;
}
```

Lưu ý: 

Nếu bạn muốn sử dụng hàm lower_bound hay upper_bound để tìm phần tử lớn nhất “bé hơn hoặc bằng” hoặc “bé hơn” bạn có thể thay đổi cách so sánh của set để tìm kiếm. Mời bạn xem chương trình sau để rõ hơn: 



```c++
#include <iostream>
#include <set>
#include <vector>
using namespace std;
int main() {
 set <int, greater <int> > s;
 set <int, greater <int> > :: iterator it; // Phép toán so sánh là greater

 s.insert(1); // s={1}
 s.insert(2); // s={2,1}
 s.insert(4); // s={4,2,1}
 s.insert(9); // s={9,4,2,1}

 /* Tim phần tử lớn nhất bé hơn hoặc bằng 5 */
 it=s.lower_bound(5);
 cout << *it << endl; // In ra 4

 /* Tim phần tử lớn nhất bé hơn 4 */
 it=s.upper_bound(4);
 cout << *it << endl; // In ra 2
 return 0
} 
```





**Map (Ánh xạ):**



* Map là một loại associative container. Mỗi phần tử của map là sự kết hợp của khóa (key value) và ánh xạ của nó (mapped value). Cũng giống như set, trong map không chứa các khóa mang giá trị giống nhau.

- Trong map, các khóa được sử dụng để xác định giá trị các phần tử. Kiểu của khóa và ánh xạ có thể khác nhau. - Và cũng giống như set, các phần tử trong map được sắp xếp theo một trình tự nào đó theo cách so sánh.
- Map được cài đặt bằng red-black tree (cây đỏ đen) – một loại cây tìm kiếm nhị phân tự cân bằng. Mỗi phần tử của map lại được cài đặt theo kiểu pair (xem thêm ở thư viện utility).





Khai báo:

```c++
#include <map>
...
map <kiểu_dữ_liệu_1,kiểu_dữ_liệu_2>
// kiểu dữ liệu 1 là khóa, kiểu dữ liệu 2 là giá trị của khóa. 
```





Sử dụng class so sánh: 

```c++
struct cmp{
 bool operator() (char a,char b) {return a<b;}
};
.....
map <char,int,cmp> m;
```

Truy cập đến giá trị của các phần tử trong map khi sử dụng iterator: Ví dụ ta đang có một iterator là it khai báo cho map thì: 



```c++
(*it).first; // Lấy giá trị của khóa, kiểu_dữ_liệu_1
 (*it).second; // Lấy giá trị của giá trị của khóa, kiểu_dữ_liệu_2
 (*it) // Lấy giá trị của phần tử mà iterator đang trỏ đến, kiểu pair

 it->first; // giống như (*it).first
 it->second; // giống như (*it).second
```



Capacity:

* size : trả về kích thước hiện tại của map. ĐPT O(1) 
* empty : true nếu map rỗng, và ngược lại. ĐPT O(1). 

Truy cập tới phần tử:

* operator [khóa]: Nếu khóa đã có trong map, thì hàm này sẽ trả về giá trị mà khóa ánh xạ đến. Ngược lại, nếu khóa chưa có trong map, thì khi gọi [] nó sẽ thêm vào map khóa đó. ĐPT O(logN) 

Chỉnh sửa:

* insert : Chèn phần tử vào map. Chú ý: phần tử chèn vào phải ở kiểu “pair”. ĐPT O(logN). 
* erase : o xóa theo iterator ĐPT O(logN) o xóa theo khóa: xóa khóa trong map. ĐPT: O(logN).
* clear : xóa tất cả set. ĐPT O(n). 
* swap : đổi 2 set cho nhau. ĐPT O(n). 

Operations: 

*  find : trả về itarator trỏ đến phần tử cần tìm kiếm. Nếu không tìm thấy iterator trỏ về “end” của map. ĐPT O(logN).
*  lower_bound : trả về iterator đến vị trí phần tử bé nhất mà không bé hơn (lớn hơn hoặc bằng) khóa (dĩ nhiên là theo phép so sánh), nếu không tìm thấy trả về vị trí “end” của map. ĐPT O(logN).
*  upper_bound: trả về iterator đến vị trí phần tử bé nhất mà lớn hơn khóa, nếu không tìm thấy trả về vị trí “end” của map. ĐPT O(logN). 
*  count : trả về số lần xuất hiện của khóa trong multiset. ĐPT O(logN) 



Demo

```c++
#include <iostream>
#include <map>
#include <vector>
using namespace std;
int main() {
 map <char,int> m;
 map <char,int> :: iterator it;

 m['a']=1; // m={{'a',1}}
 m.insert(make_pair('b',2)); // m={{'a',1};{'b',2}}
 m.insert(pair<char,int>('c',3) ); // m={{'a',1};{'b',2};{'c',3}}

 cout << m['b'] << endl; // In ra 2
 m['b']++; // m={{'a',1};{'b',3};{'c',3}}

 it=m.find('c'); // it point to key 'c'

 cout << it->first << endl; // In ra 'c'
 cout << it->second << endl; // In ra 3

 m['e']=100; //m={{'a',1};{'b',3};{'c',3};{'e',100}}

 it=m.lower_bound('d'); // it point to 'e'
 cout << it->first << endl; // In ra 'e'
 cout << it->second << endl; // In ra 100

 return 0;
} 
```





**Duyệt map**

```c++
map<int, char*> mymap, copymymap;
mymap[0] = "a";
mymap[1] = "b";
mymap[0] = "c";

cout << mymap.size();
```



**Kiểm tra map có rỗng hay không**

```c++
map<int, char*> mymap, copymymap;
mymap[0] = "a";
mymap[1] = "b";
mymap[0] = "c";

if (copymymap.empty()) cout << "copymymap is empty";
```





**Truy xuất theo chỉ số**

```c++
map<int, char*> mymap, copymymap;
mymap[0] = "a";
mymap[1] = "b";

cout << mymap[1] << " " << mymap.at(0);
```





**Xóa bỏ một phần tử trong map**



```c++
map<int, char*> mymap, copymymap;
mymap[0] = "a";
mymap[1] = "b";
mymap[5] = "c";
mymap[7] = "d";
mymap[9] = "e";

// xóa cặp đối tượng với "key" là 5
mymap.erase(5);		
// => mymap =  {(0,"a"),(1,"b"),(7,"d"),(9,"e")}
	
map<int, char*>::iterator var = mymap.begin();
// xóa cặp đối tượng mà var đang truy cập
mymap.erase(var); // => mymap =  {(1,"b"),(7,"d"),(9,"e")}

var = mymap.find(7); // => var truy cập đến (7,"d")

// xóa từ vị trí var đang truy cập cho đến (9,"e") 
mymap.erase(var, mymap.end()); // => mymap = {(1,"b")}
```



**Xóa tất cả phần tử trong map**

```c++
map<int, char*> mymap;
mymap[0] = "a";
mymap[1] = "b";
mymap[5] = "c";
mymap[7] = "d";
mymap[9] = "e";

mymap.clear();		
// => mymap =  {}
```



**Hoán đổi nội dung 2 map**

```c++
map<char,int> map1, map2;

map1['x'] = 100;
map1['y'] = 200;

map2['a'] = 11;
map2['b'] = 22;
map2['c'] = 33;

map1.swap(map2);
// => map1 = {("x",11),("b",22),("c",33)}
// => map2 = {("x",100),("y",200)}
```



Các bài tập hay gặp mình sẽ tiếp tục update ở dưới

.....

....







Một số tài liệu tham khảo



https://vncoder.vn

https://www.cplusplus.com/reference/map/map/

https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/









