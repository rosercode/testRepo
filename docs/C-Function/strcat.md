# C 库函数 - strcat()

[![C 标准库 - ](E:\Desktop\C\C-Function\strcat.assets\up.gif) C 标准库 - ](https://www.runoob.com/cprogramming/c-standard-library-string-h.html)

## 描述

C 库函数 **char \*strcat(char \*dest, const char \*src)** 把 **src** 所指向的字符串追加到 **dest** 所指向的字符串的结尾。

## 声明

下面是 strcat() 函数的声明。

```
char *strcat(char *dest, const char *src)
```

## 参数

- **dest** -- 指向目标数组，该数组包含了一个 C 字符串，且足够容纳追加后的字符串。
- **src** -- 指向要追加的字符串，该字符串不会覆盖目标字符串。

## 返回值

该函数返回一个指向最终的目标字符串 dest 的指针。

## 实例

下面的实例演示了 strcat() 函数的用法。

```c
#include <stdio.h>
#include <string.h>
 
int main ()
{
   char src[50], dest[50];
 
   strcpy(src,  "This is source");
   strcpy(dest, "This is destination");
 
   strcat(dest, src);
 
   printf("最终的目标字符串： |%s|", dest);
   
   return(0);
}
```

让我们编译并运行上面的程序，这将产生以下结果：

```
最终的目标字符串： |This is destinationThis is source|
```

值得注意的是，我们是不能使用这个函数，来把一个字符串和一个字符来拼接

我们可以使用下面这个函数来完成字符串和字符的拼接

```c
// 向字符串最后追加一个字符
void appendChar(char *string, char char1)
{
    int length = strlen(string);
    string[length] = char1;
    string[length + 1] = 0;
}

void appendChar(char *string, char char1)
{
    int length = 0 , i;
    for(i = 0 ; i < string[i]!=0 ; i++){
		length ++ ;
    }
	string[length] = char1;
    string[length+1] = 0;
}
```

