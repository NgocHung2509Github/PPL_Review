Công thức chung: $-1^{sign} * 2^{exponent-bias} * (1 + fraction)$

\* số âm $sign$ = 1, số dương $sign$ = 0

### Half precision
___
Xem chi tiết: [Half precision](https://en.wikipedia.org/wiki/Half-precision_floating-point_format)

#### Size:

- Sign bit: 1 bit
- Exponent: 5 bits
- Fraction: 10 bits

#### Công thức:

- $bias=2^{5-1}-1=15$
- $exponent=\sum_{i=0}^{4} b_i*2^i$
- $fraction=\sum_{i=1}^{10} b_{10-i}*2^{-i}$

### Single precision
___
Xem chi tiết: [Single precision](https://en.wikipedia.org/wiki/Single-precision_floating-point_format)

#### Size:

- Sign bit: 1 bit
- Exponent: 8 bits
- Fraction: 23 bits

#### Công thức:

$bias=2^{8-1}-1$
$exponent=\sum_{i=0}^{7} b_i*2^i$
$fraction=\sum_{i=1}^{23} b_{23-i}*2^{-i}$

### Double precision
___
Xem chi tiết: [Double precision](https://en.wikipedia.org/wiki/Double-precision_floating-point_format)

#### Size:

- Sign bit: 1 bit
- Exponent: 11 bits
- Fraction: 52 bits

#### Công thức:

$bias=2^{11-1}-1$
$exponent=\sum_{i=0}^{10} b_i*2^i$
$fraction=\sum_{i=1}^{52} b_{52-i}*2^{-i}$