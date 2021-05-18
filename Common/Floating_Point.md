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
- Single-Precision(32-bit, float in C)  
- Double-Precision(64-bit, double in C)  

**S(Sign)** 
- 부호비트. MSB(최상위비트)에 표현된다.
- **0** 일 때 양수, **1** 일 때 음수이다.  
- ㅇㄴㅇㄹㄴ

E(Exponent) : 지수부(2의 승수)를 나타냅니다.  
M(Mantissa) : Significand 또는 Mantissa에 해당하는 부분입니다.   




S : Sign
  - M

E는 30 ~ 23번 비트에 표현되며 3가지로 구분됩니다.    
    - Normalized Values : 0000_0001 ~ 1111_1110, 
    - Denomalized Values
    - Special Values
3. M은 22 ~ 0번 비트에 표현됩니다.  
    - E가 0이 아닌 경우(Normalized Values) 맨 앞의 1이 생략된 것으로 인코딩 됩니다. ex) 0100...1111 -> 10100...1111
