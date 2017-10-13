# Rcpp algorithms, Compare R and C++

### cppFunction & sourceCpp
```r
(require (Rcpp))

(cppFunction ('int one() {
  return 1;
}'))

(one ()) #=> "[1] 1" 标量输出
```
* fib_cpp_1.cpp
```c++
#include <Rcpp.h>
using namespace Rcpp;

//[[Rcpp::export]]
int fib_cpp_1(int n)
{
    if(n==1||n==2) return 1;
    return fib_cpp_1(n-1)+fib_cpp_1(n-2);
}
```
```r

> require(Rcpp)
载入需要的程辑包：Rcpp
>

>  sourceCpp('fib_cpp_1.cpp')

> fib_cpp_1(50)
[1] -298632863

> fib_cpp_1(10)
[1] 55
> fib_cpp_1(20)
[1] 6765
> fib_cpp_1(30)
[1] 832040

> system.time(fib_cpp_1(50))
  用户   系统   流逝
27.053  0.356 28.620
>

```
### Matrix & Vector
```r
```

