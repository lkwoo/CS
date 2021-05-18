# IEEE Standard for Floating-Point Arithmetic (IEEE 754)
```
부동소수점을 다음과 같이 표현할 수 있다.  
V = x * 2^y  
이 방식은 매우 큰 수와 작은 수를 표현하는데 유용하다.  
IEEE-754 표준을 통해 부동소수점의 표현식과 연산에 대해 알아보자.  
```

## IEEE Floating-Point Representation
IEEE 표준 표현식은 다음과 같다.  
***V = (-1)^S * M * 2^E***  
- S : 부호비트. 0 일 때 양수, 1 일 때 음수이다.  
- E : 지수부(2의 승수)를 나타냅니다.  
- M : Significand 또는 Mantissa에 해당하는 부분입니다.   

32-Bit와 64-Bit 두 가지 타입이 있습니다.  
- Single-Precision(32-bit, float in C)
- Double-Precision(64-bit, double in C)

### Single-Precision(32-bit)

32 비트 그림  

1. S는 MSB에 표현됩니다.
2. E는 30 ~ 23번 비트에 표현되며 3가지로 구분됩니다.
  - Normalized Values 
  - Denomalized Values
  - Special Values
3. M은 22 ~ 0번 비트에 표현됩니다.  
  - E가 0이 아닌 경우(Normalized Values) 맨 앞의 1이 생략된 것으로 인코딩 됩니다. ex) 0100...1111 -> 10100...1111
