# 代码片段

## 完全平方数

```c
#include <stdio.h>

int IsSquare(int n);

int main(){
    int n;

    scanf("%d", &n);
    
    if (IsSquare(n))  
        printf("YES\n");
    else  
        printf("NO\n");

    return 0;
}

int IsSquare(int n){
    if (n < 0)   return 0;  // 不能够是负数
    for (size_t i = 0; i <= n; i++) // 此处应该是等号，考虑 1 情况
        if (i * i == n)   
            return 1;
    return 0;
}
```


## 素数和合数

- 代码:

```c
 // 2020-11-13 12:26:33
 
#include <stdio.h>
#include <math.h>

int prime(int p);
int PrimeSum(int m, int n);
int main(){
    int m, n, p;

    scanf("%d %d", &m, &n);
    printf("Sum of ( ");
    for (p = m; p <= n; p++)
        if (prime(p) != 0){
            printf("%d ", p);
        }
    printf(") = %d\n", PrimeSum(m, n));

    return 0;
}

int prime(int p){
    for (int i = 2; i < p/2; i++)
        if (p % i == 0) 
            return 0;
    if (p <= 1)  
        return 0;
    return 1;
}
int PrimeSum(int m, int n){
    int sum = 0;
    for (int i = m; i <= n; i++)
        if (prime(i))
            sum += i;
    return sum;
}
```

  - 注意：

    1. 素数：质数又称素数。一个大于1的自然数，除了1和它自身外，不能被其他自然数整除的数叫做质数

  2. 合数：合数是指在大于1的整数中除了能被1和本身整除外，还能被其他数（0除外）[整除](https://baike.baidu.com/item/整除/2452641)的数

     注：0 既不是素数也不是合数。2 是唯一一个是偶数的素数。

  3. 注：这个编程题要考虑负数的情况。

```c
#include <stdio.h>

/*  
- TIME：2020-11-11 21:16:09 
	- 函数fact应返回n的阶乘，建议用递归实现。
	- 函数factsum应返回 1!+2!+...+n! 的值。题目保证输入输出在双精度范围内。
*/

double fact(int n);
double factsum(int n);

int main(){
    int n;
    scanf("%d", &n);
    printf("fact(%d) = %.0f\n", n, fact(n));
    printf("sum = %.0f\n", factsum(n));
    return 0;
}
double fact(int n){
    if (n == 1 || n == 0)
        return 1;
    else 
        return n * fact(n - 1);
}
double factsum(int n){
    double sum = 0;
    for (int i = 1; i <= n; i++){
        sum += fact(i);
    }
    return sum;
}
```

要考虑求0的阶乘的情况，0的阶乘是0

## 拼接字符串

- 代码

```c
char *str_cat(char *s, char *t)
{
    for (int i = 0;; i++)
        if (s[i] == 0){
            for (int j = 0; t[j] != 0; j++){
                s[i + j] = t[j];
                if (t[j] == 0)
                    s[i + j + 1] = 0;
            }
            break;
        }
    return s;
}
```

  


## 求最大公约数

- 代码：

```c
// 2020-11-13 19:51:05

#include <stdio.h>

int gcd(int x, int y);

int main(){
    int x, y;

    scanf("%d %d", &x, &y);
    printf("%d\n", gcd(x, y));

    return 0;
}
int gcd(int x, int y){
    int max = 1;
    for (int i = 2; i < (x < y ? y : x); i++)
        if (x % i == 0 && y % i == 0)
            max = i;
    return max;
}
```

  这是一种思路

  


