<!--     範例       -->

### 
<!--                 
# \[{  \color{Fuchsia}精\;銳\; \color{Purple}矩\;陣\;  \color{Red}計\;算\; \color{Green} 求\;解\;器  }\] 
-->  
![](Images/11-10-01.png) 


<!--         
#### \[{  \color{Fuchsia} 【 \color{Green}  Sharp \; Matrix \; Solver \;  \color{Brown} \iff  \;  \color{Red} S\;M\;S】 }\]  
-->  
![](Images/11-10-02.png)  



##
## 

# 矩 陣 計 算 的 運 算 子 共 計 有 12 個 ：  

---  

### 第一個是加 [+] 
```CSharp 
using System;
using Matrix_0; 

namespace ConsoleApp7
{
    internal class Program
    {
        static void Main(string[] args)
        {

// A 是複數矩陣
double[,] A0 = {{5, -3, -9}, {4, -6, 0}}; 
// 將 A0 矩陣轉爲 ReMatrix 型態。
ReMatrix A = new ReMatrix(A0); 
double[,] B = {{-2, 4, 9}, {9, 7, -4}};
Console.WriteLine("A 矩陣 ： \n{0}\n", new PR(A)); 
Console.WriteLine("B 矩陣 ： \n{0}\n", new PR(B)); 

// C 矩陣是 A + B 矩陣。 
ReMatrix C = A + B;   
Console.WriteLine("\n C 矩陣(即 A + B)  : \n{0}\n", 
    new PR(C)) ;

        }
    }
}
/*  輸出結果如下 :
A 矩陣 ：
        5.00000         -3.00000         -9.00000
        4.00000         -6.00000          0.00000

B 矩陣 ：
       -2.00000          4.00000          9.00000
        9.00000          7.00000         -4.00000

 C 矩陣(即 A + B)  :
        3.00000          1.00000          0.00000
       13.00000          1.00000         -4.00000

請按任意鍵繼續 . . .
*/

```
### 第二個是減 [-] 

### 第三個是乘 [*] 
```CSharp 
using System;
using Matrix_0; 

namespace ConsoleApp7
{
    internal class Program
    {
        static void Main(string[] args)
        {

double[,] A0 = {{4, -3, 9}, {9, -3, -6}, {15, 7, -7} }; 
double[,] A1 = {{-5, -3, 9}, {7, 8, 0}, {-9, 5, 4} }; 
ReMatrix A = (ReMatrix)A0 * A1; 
Console.WriteLine("A0 矩陣 ： \n{0}\n", new PR(A0)); 
Console.WriteLine("A1 矩陣 ： \n{0}\n", new PR(A1)); 
Console.WriteLine("A0 * A1 = \n{0}\n", new PR(A)) ; 

        }
    }
}
/*  輸出結果如下 :
A0 矩陣 ：
        4.00000         -3.00000          9.00000
        9.00000         -3.00000         -6.00000
       15.00000          7.00000         -7.00000

A1 矩陣 ：
       -5.00000         -3.00000          9.00000
        7.00000          8.00000          0.00000
       -9.00000          5.00000          4.00000

A0 * A1 =
     -122.00000          9.00000         72.00000
      -12.00000        -81.00000         57.00000
       37.00000        -24.00000        107.00000

請按任意鍵繼續 . . .
*/
```

### 第四個是除 [/] 
```CSharp 
using System;
using Matrix_0; 

namespace ConsoleApp7
{
    internal class Program
    {
        static void Main(string[] args)
        {

double[,] A0 = {{4, -3, 9}, {9, -3, -6}, {15, 7, -7} }; 
double[,] A1 = {{-5, -3, 9}, {7, 8, 0}, {-9, 5, 4} }; 
ReMatrix A = (ReMatrix)A0 / A1; 
Console.WriteLine("A0 矩陣 ： \n{0}\n", new PR(A0)); 
Console.WriteLine("A1 矩陣 ： \n{0}\n", new PR(A1)); 
Console.WriteLine("A0 / A1 = \n{0}\n", new PR(A)) ; 

        }
    }
}
/*  輸出結果如下 :
A0 矩陣 ：
        4.00000         -3.00000          9.00000
        9.00000         -3.00000         -6.00000
       15.00000          7.00000         -7.00000

A1 矩陣 ：
       -5.00000         -3.00000          9.00000
        7.00000          8.00000          0.00000
       -9.00000          5.00000          4.00000

A0 / A1 =
        1.32469          0.57835         -0.73055
       -0.30440          0.02029         -0.81511
       -0.52424          1.03495         -0.57046

請按任意鍵繼續 . . .
*/
```

### 第五個是是否相等 [==] 
```CSharp 
using System;
using Matrix_0; 

namespace ConsoleApp7
{
    internal class Program
    {
        static void Main(string[] args)
        {

double[,] A0 = {{4.00000, -3, 9}, {9, -3, -6}, {15, 7, -7} }; 
double[,] A1 = {{4.00001, -3, 9}, {9, -3, -6}, {15, 7, -7} }; 
Console.WriteLine("A0 矩陣 ： \n{0}\n", new PR(A0)); 
Console.WriteLine("A1 矩陣 ： \n{0}\n", new PR(A1)); 

bool bValue =  (ReMatrix)A0 == A1 ; 
if( bValue == true )
{
    Console.WriteLine("\n  **  兩個矩陣相等!  **\n "); 
}
else 
    Console.WriteLine("\n  **  兩個矩陣不相等!  **\n ");

        }
    }
}
/*  輸出結果如下 :
A0 矩陣 ：
        4.00000         -3.00000          9.00000
        9.00000         -3.00000         -6.00000
       15.00000          7.00000         -7.00000

A1 矩陣 ：
        4.00001         -3.00000          9.00000
        9.00000         -3.00000         -6.00000
       15.00000          7.00000         -7.00000

  **  兩個矩陣不相等!  **

請按任意鍵繼續 . . .
*/

```

### 第六個是否不相等 [！=] 

### 第七個是矩陣水平合併 [&] 
```C# 
using System;
using Matrix_0; 

namespace ConsoleApp7
{
    internal class Program
    {
        static void Main(string[] args)
        {

double[,] A = {{3, 6, 7}, {-4, 2, 9}}; 
double[,] B = {{-1, 8, -4}, {-9, 2, 0}}; 
Console.WriteLine("A 矩陣 ： \n{0}\n", new PR(A)); 
Console.WriteLine("B 矩陣 ： \n{0}\n", new PR(B)); 

ReMatrix C =  (ReMatrix)A & B; 
Console.WriteLine("\n C 矩陣 = A & B :\n{0}\n",  new PR(C)) ;

        }
    }
}
/*  輸出結果如下 :
A 矩陣 ：
        3.00000          6.00000          7.00000
       -4.00000          2.00000          9.00000

B 矩陣 ：
       -1.00000          8.00000         -4.00000
       -9.00000          2.00000          0.00000

 C 矩陣 = A & B :
  3.00000    6.00000    7.00000   -1.00000     8.00000   -4.00000
 -4.00000    2.00000    9.00000   -9.00000     2.00000    0.00000

請按任意鍵繼續 . . .
*/

```

### 第八個是矩陣垂直合併 [|] 
```C#
using System;
using Matrix_0; 

namespace ConsoleApp7
{
    internal class Program
    {
        static void Main(string[] args)
        {

double[,] A = {{3, 6, 7}, {-4, 2, 9}}; 
double[,] B = {{-1, 8, -4}, {-9, 2, 0}}; 
Console.WriteLine("A 矩陣 ： \n{0}\n", new PR(A)); 
Console.WriteLine("B 矩陣 ： \n{0}\n", new PR(B)); 

ReMatrix C =  (ReMatrix)A | B; 
Console.WriteLine("\n C 矩陣 = A | B (即兩矩陣垂直合併):\n{0}\n",  new PR(C)) ;

        }
    }
}
/*  輸出結果如下 :
A 矩陣 ：
        3.00000          6.00000          7.00000
       -4.00000          2.00000          9.00000

B 矩陣 ：
       -1.00000          8.00000         -4.00000
       -9.00000          2.00000          0.00000

 C 矩陣 = A | B (即兩矩陣垂直合併):
        3.00000          6.00000          7.00000
       -4.00000          2.00000          9.00000
       -1.00000          8.00000         -4.00000
       -9.00000          2.00000          0.00000

請按任意鍵繼續 . . .
*/

```
### 第九個是向量内積 [^]  
```CSharp 
using System;
using Matrix_0; 

namespace ConsoleApp7
{
    internal class Program
    {
        static void Main(string[] args)
        {

double[,] A = {{13}, {6}, {7} }; 
double[,] B = {{-11}, {8}, {-4}}; 
Console.WriteLine("A 矩陣 ： \n{0}\n", new PR(A)); 
Console.WriteLine("B 矩陣 ： \n{0}\n", new PR(B)); 

ReMatrix C =  (ReMatrix)A ^ B; 
Console.WriteLine("\n C 矩陣 = A ^ B (即向量內積):\n{0}\n",  new PR(C)) ;

        }
    }
}
/*  輸出結果如下 :
A 矩陣 ：
       13.00000
        6.00000
        7.00000

B 矩陣 ：
      -11.00000
        8.00000
       -4.00000

 C 矩陣 = A ^ B (即向量內積):
     -123.00000

請按任意鍵繼續 . . .
*/

```

---  

### 第十個是逆矩陣 [～] ， 為 Unit Operator
```CSharp
using System;
using Matrix_0; 

namespace ConsoleApp7
{
    internal class Program
    {
        static void Main(string[] args)
        {

// A 是複數矩陣
double[,] Are = {{13, 3, 9}, {6, -5, 2}, {-7, 4, 7} }; 
double[,] Aim = {{-11, 5, 8}, {8, -6, -2}, {-4, -8, -1}}; 
CxMatrix A = new CxMatrix(Are, Aim); 
Console.WriteLine("A 矩陣 ： \n{0}\n", new PR(A)); 

// A 矩陣的逆矩陣是 Ai 矩陣。 
CxMatrix Ai =  ~A;  
Console.WriteLine("\n Ai 矩陣(即 A 矩陣的逆矩陣)  : \n{0}\n",  new PR(Ai)) ;

// ***  以下是檢核 Ai 矩陣是否為 A 矩陣的逆矩陣？  *** 
// 設 B = A * Ai 。 B 矩陣雖然是複數，但發現其虛數值為零，故可轉換為 Breal 實數矩陣。
// Breal 矩陣是單位矩陣，故證明 A 矩陣的逆矩陣是 Ai 矩陣是對的。
CxMatrix B = A * Ai ; 
Console.WriteLine("\n B 矩陣 : \n{0}\n", new PR(B));

ReMatrix Breal = (ReMatrix)B; 
Console.WriteLine("\n Breal 矩陣 \n{0}\n\n", new PR(Breal));  

        }
    }
}
/*  輸出結果如下 :
A 矩陣 ：
  13.00000 -   11.00000i,        3.00000  +         5.00000i,        9.00000  +         8.00000i
   6.00000 +    8.00000i,       -5.00000  -         6.00000i,        2.00000  -         2.00000i
  -7.00000 -    4.00000i,        4.00000  -         8.00000i,        7.00000  -         1.00000i

 Ai 矩陣(即 A 矩陣的逆矩陣)  :
  -0.02784  -         0.03163i,        0.11726  -         0.03601i,       -0.03937  +         0.11065i
  -0.05227  -         0.08554i,        0.11627  +         0.06228i,       -0.10586  +         0.17003i
   0.12368  -         0.04073i,       -0.01774  +         0.12575i,       -0.07350  -         0.14049i

 B 矩陣 :
   1.00000  +         0.00000i,        0.00000  +         0.00000i,        0.00000  +         0.00000i
   0.00000  +         0.00000i,        1.00000  +         0.00000i,        0.00000  +         0.00000i
   0.00000  +         0.00000i,        0.00000  +         0.00000i,        1.00000  +         0.00000i

 Breal 矩陣
        1.00000          0.00000          0.00000
        0.00000          1.00000          0.00000
        0.00000          0.00000          1.00000

請按任意鍵繼續 . . .
*/

```
### 第十一個是轉置 [！] ， 為 Unit Operator
```CSharp 
using System;
using Matrix_0; 

namespace ConsoleApp7
{
    internal class Program
    {
        static void Main(string[] args)
        {

// A 是複數矩陣
double[,] Are = {{13, 3, 9}, {6, -5, 2}, {-7, 4, 7} }; 
double[,] Aim = {{-11, 5, 8}, {8, -6, -2}, {-4, -8, -1}}; 
CxMatrix A = new CxMatrix(Are, Aim); 
Console.WriteLine("A 矩陣 ： \n{0}\n", new PR(A)); 

// A 矩陣的轉置矩陣是 At 矩陣。 
CxMatrix At =  !A;  
Console.WriteLine("\n At 矩陣(即 A 矩陣的轉置矩陣)  : \n{0}\n",  new PR(At)) ;

        }
    }
}
/*  輸出結果如下 :
A 矩陣 ：
 13.00000 -  11.00000i,  3.00000 +   5.00000i,  9.00000 +   8.00000i
  6.00000 +   8.00000i, -5.00000 -   6.00000i,  2.00000 -   2.00000i
 -7.00000 -   4.00000i,  4.00000 -   8.00000i,  7.00000 -   1.00000i

 At 矩陣(即 A 矩陣的轉置矩陣)  :
 13.00000 -  11.00000i,  6.00000 +   8.00000i, -7.00000 -   4.00000i
  3.00000 +   5.00000i, -5.00000 -   6.00000i,  4.00000 -   8.00000i
  9.00000 +   8.00000i,  2.00000 -   2.00000i,  7.00000 -   1.00000i

請按任意鍵繼續 . . .
*/

```
### 第十二個是單位向量 [+] ， 為 Unit Operator  
```CSharp 
using System;
using Matrix_0; 

namespace ConsoleApp7
{
    internal class Program
    {
        static void Main(string[] args)
        {

// A 是複數矩陣
double[,] A = {{18}, {-3}, {-9} };  
Console.WriteLine("A 矩陣 ： \n{0}\n", new PR(A)); 

// A 矩陣的單位矩陣是 At 矩陣。 
ReMatrix Aunit =  +( (ReMatrix)A );  
Console.WriteLine("\n Aunit 矩陣(即 A 矩陣的單位矩陣)  : \n{0}\n", 
    new PR(Aunit)) ;

        }
    }
}
/*  輸出結果如下 :
A 矩陣 ：
       18.00000
       -3.00000
       -9.00000

 Aunit 矩陣(即 A 矩陣的單位矩陣)  :
        0.88465
       -0.14744
       -0.44233

請按任意鍵繼續 . . .
*/

```
#

# [精 銳 科 技【矩陣計算求解器開發】](https://www.github.com/myyeh2/App_CSharp) 

######

![](Images/name_card.png)  

##
##
