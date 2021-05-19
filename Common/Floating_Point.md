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

32-Bit와 64-Bit 두 가지 타입이 있다. 비트 수에 따라 표현할 수 있는 범위와 정확도의 차이만 있고 원리는 같다.  
1. Single-Precision(32-bit, float in C)  
2. Double-Precision(64-bit, double in C)  

**S(Sign)** 
- 부호비트. MSB(최상위비트)에 표현된다.
- **0** 일 때 양수, **1** 일 때 음수이다.  

**E(Exponent)**
- 지수부(2의 승수)를 나타냅니다.  
- Single-Precision은 8bit, Double_Precision은 11bit로 표현되며 3가지로 구분됩니다. 아래 예시는 Single-Precision입니다.
    1. Normalized Values : 0000_0001 ~ 1111_1110 // -126 ~ 127
        - bias가 적용됩니다. n bit로 이루어졌을 때, 2^(N-1) - 1 를 뺀 값으로 encode 됩니다. 즉 1 - 127 = -126이 최소값입니다.
        - sign이 아니라 bias를 적용하는 이유는 값을 비교하기 훨씬 편하기 때문입니다.
        - 아래의 M에도 영향을 줍니다. 앞에 1이 생략되었다고 가정합니다. 예를 들어 M이 0100...1011라면 10100...1011로 해석합니다.
    2. Denomalized Values : 0000_0000
    3. Special Values : 모든 bit가 1
        - M == 0 : +Inf, -Inf (Sign을 따른다)
        - M != 0 : NaN(Not a Number)

**M(Mantissa)**
- Significand 또는 Mantissa에 해당하는 부분입니다.   
- M은 22 ~ 0번 비트에 표현됩니다.  
- E가 0이 아닌 경우(Normalized Values) 맨 앞의 1이 생략된 것으로 인코딩 됩니다. ex) 0100...1111 -> 10100...1111
