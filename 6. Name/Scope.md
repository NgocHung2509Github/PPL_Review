### Definition
___
Scope của một sự ràng buộc (binding) là một vùng của chương trình mà trong đó, ràng buộc có hiệu lực

Xem chí tiết tại: [Static and Dynamic scoping](https://www.geeksforgeeks.org/static-and-dynamic-scoping/)
Xem các video này để dễ hiểu hơn:
- [Neso - #1](https://www.youtube.com/watch?v=L53nqHCSSFY)
- [Neso - #2](https://www.youtube.com/watch?v=DeGfInd5BPY)

### Static/Lexical scoping
___
Scope của một biến được xác định bởi vị trí của nó trong source code, thường dựa trên nơi nó được khai báo. Một biến sẽ được refer đến môi trường cấp cao nhất mà nó được khai báo.

Ví dụ:
```
// A C program to demonstrate static scoping.
#include<stdio.h>
int x = 10;

// Called by g()
int f()
{
return x;
}

// g() has its own variable
// named as x and calls f()
int g()
{
int x = 20;
return f();
}

int main()
{
printf("%d", g());
printf("\n");
return 0;
}
```

Output: `10`

### Dynamic scoping
___
Scope của một biến được xác định bởi chuỗi các lệnh gọi hàm dẫn đến điểm thực thi hiện tại. Một biết sẽ được refer đến môi trường gần nhất mà nó được khai báo.

Ví dụ:
```
// A C program to demonstrate dynamic scoping.
#include<stdio.h>
int x = 10;

// Called by g()
int f()
{
return x;
}

// g() has its own variable
// named as x and calls f()
int g()
{
int x = 20;
return f();
}

int main()
{
printf("%d", g());
printf("\n");
return 0;
}
```

Output: `20`
