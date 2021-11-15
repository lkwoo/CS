# IEEE Standard for Floating-Point Arithmetic (IEEE 754)
```
부동소수점을 다음과 같이 표현할 수 있다.  
V = x * 2^y  
이 방식은 매우 큰 수와 작은 수를 표현하는데 유용하다.  
IEEE-754 표준을 통해 부동소수점의 표현식과 연산에 대해 알아보자.  
```

## IEEE Floating-Point Representation
IEEE 표준 표현식은 다음과 같다.  
> ***V = (-1)^S * M * 2^E***  

32-Bit와 64-Bit 두 가지 타입이 가장 많이 쓰인다. 그 중 64-bit가 더 잘 쓰인다. 비트 수에 따라 표현할 수 있는 범위와 정확도의 차이만 있고 원리는 같다.  
1. Single-Precision(32-bit, float in C)  
    - Sign 1 bit, Exponent  8 bits, Mantissa 23 bits 
2. Double-Precision(64-bit, double in C)  
    - Sign 1 bit, Exponent 11 bits, Mantissa 52 bits 


**S(Sign)** 
- 부호비트. MSB(최상위비트)에 표현된다.
- **0** 일 때 양수, **1** 일 때 음수이다.  

**E(Exponent)**
- 지수부(2의 승수)를 나타냅니다.  
- Single-Precision은 8bit, Double_Precision은 11bit로 표현되며 3가지로 구분됩니다. 아래 예시는 Single-Precision입니다.
    1. Normalized Values : 0000_0001 ~ 1111_1110 // -126 ~ 127
        - bias가 적용됩니다. n bit로 이루어졌을 때, 2^(N-1) - 1 를 뺀 값으로 encode 됩니다. 즉 1 - 127 = -126이 최소값입니다.
        - sign이 아니라 bias를 적용하는 이유는 값을 비교하기 훨씬 편하기 때문입니다.
        - 아래의 M에도 영향을 줍니다. 앞에 1이 생략되었다고 가정합니다. 예를 들어 M이 0100...1011라면 10100...1011로 해석합니다.(1bit 이득^^)
    2. Denomalized Values : 0000_0000, E의 모든 bit가 0
    3. Special Values : 1111_1111, E의 모든 bit가 1
        - M == 0 : +Inf, -Inf (Sign을 따른다)
        - M != 0 : NaN(Not a Number)

**M(Mantissa)**
- Significand 또는 Mantissa에 해당하는 부분입니다.   
- M은 22 ~ 0번 비트에 표현됩니다.  
- E가 0이 아닌 경우(Normalized Values) 맨 앞의 1이 생략된 것으로 인코딩 됩니다. ex) 0100...1111 -> 10100...1111

## IEEE Floating-Point Rounding
- 무한히 많은 실수를 유한개의 비트로 표현하기 위해서는 근사적으로 표현해야 한다.
- 정수 연산과는 달리, 연산 결과를 32 혹은 64개의 비트로 정확히 표현 가능한 경우는 드물다.
- 따라서 반올림을 사용하고 이로 인한 오차는 필연적이고, 그 오차를 측정할 수 있어야 한다.
- 반올림이 만드는 오차는 예상보다 클 수 있다. (catastrophic cancellation 참고)
- Ex) b=3.34, a=1.22, c=2.28 일 때, b^2 - 4ac = 0.0292 이지만 b^2=11.2, 4ac=11.1로 반올림되면 0.1이다.
- 
### Round to Even
- 12.5를 반올림하면 12인가 13인가?
- 'Reiser and Knuth [1975]'에 따르면 짝수가 되도록 반올림 하는 것이 효과적이다.
- 즉, 12.35의 소수 2째 자리에서 반올림 하면 12.4, 12.25의 소수 2째 자리에서 반올림하면 12.2가 된다.

### 곱셈의 반올림 오차 최소화
- 실수 X, Y의 곱 XY를 계산할 때, 를 X = Xh + Xl, Y = Yh + Yl로 변환하여 곱한다.
- Xh와 Xl은 ((X의 비트수) / 2)개의 비트로 표현한다. 홀수라면 빼기를 활용.
- ex) X = 0.10111 일 때, Xh = 0.11, Xl = -0.00001

## IEEE Floating-Point Operation
- 부동소수점의 덧셈은 결합법칙이 성립하지 않는다. (교환법칙은 성립)
``` c++
double x, y, x;
x = pow(10, 30);
y = -x;
z = 1;

cout << x + (y + z) << endl; // print : 0
cout << (x + y) + z << endl; // print : 1
```

[참고](https://nybounce.wordpress.com/2016/06/24/ieee-754-floating-point%EB%B6%80%EB%8F%99%EC%86%8C%EC%88%98%EC%A0%90-%EC%82%B0%EC%88%A0%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC/)
