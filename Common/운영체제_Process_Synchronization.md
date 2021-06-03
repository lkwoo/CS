# ProcessSynchronization
- 다중 프로그래밍 시스템
- 프로세스들은 서로 독립적
- 공유 자원 또는 데이터가 있을 때, 문제 발생 가능

## 동기화(Synchronization)
- 프로세스들이 서로 동작을 맞추는 것
- 프로세스들이 서로 정보를 공유하는 것
    - Shared Data : 여러 프로세스들이 공유하는 데이터
    - Critical Section : 공유 데이터를 접근하는 코드 영역
    - Mutual Exclusion : Critical Section에 둘 이상의 프로세스의 접근을 막는 것

## Critical Section
- Machine Instruction 하나하나는 Atomic하게 수행. 그러나 그 사이사이는 아니다.
- 여러 Process가 Critical Section에 동시 접근할 경우 결과가 잘못될 수 있다.
- 이렇게 위험한 경우를 **Race Condition**이라고 한다.

## Mutual Exclusion
### 3가지 조건  
1. Mutual Exclusion(상호배제) : Critical Section에 다른 Process가 있으면 진입 금지
2. Progress(진행) : CS안의 Process 외에는 CS에 진입하는 것을 방해하면 안 됨
3. Bounded Waiting(한정대기) : Process의 CS진입은 유한시간 내에 허용되어야함

## SW Mutual Exclusion Solution
- Dekker's Algorithm
    - Two Process ME를 보장하는 최초의 알고리즘
    - Flag와 Turn 모두 사용.
    - Flag로 1차 확인, Turn으로 2차 확인
- Dijkstra
    - N-Process ME 해결
- SW 방법 특징
    - 속도가 느림
    - 구현 복잡
    - Busy Waiting

## HW Mutual Exclusion Solution
- TAS(Test And Set) Instruction
    - Test와 Set을 한 번에 수행하는 기계어
    - 실행 중 Interrupt를 받지 않음
- HW 방법 특징
    - 구현이 간단
    - Busy Waiting -> Semaphore 사용

## OS Mutual Exclusion Solution
- Spinlock
    - 정수 변수 : 초기화, P(), V() 연산으로 접근 가능. OS가 Atomic하게 보장
    - P(S) : 접근할 때
    - V(S) : 나올 때
    - 멀티프로세서에서만 사용 가능
    - Busy Waiting
- Semaphore
    - 음이 아닌 정수형 변수 S : 초기화, P(), V() 연산으로 접근 가능. OS가 Atomic하게 보장
    - P(S) : 접근할 때. Probern
    - V(S) : 나올 때. Verhogen
    - 임의의 변수 S하나에 Ready Queue 하나가 할당 됨
    - Binary Semaphore : 상호배제, 프로세스 동기화
    - Counting Semaphore : 생산자 소비자 문제
    - **No Busy Waiting** : 기다려야 하는 프로세스는 Block 됨
    - Starvation 가능

## Producer-Consumer Problem
- Producer Producer : 메시지를 생성하는 프로세스 그룹
- Consumer Producer : 메시지를 전달받는 프로세스 그룹

|Producer        |Shared Memory Buffer |Consumer        |
|----------------|---------------------|----------------|
|Printer Driver  |Text                 |Printer         |
|Compiler        |Assembly Code        |Assembler       |
|Assembler       |Module               |Loader          |

- Producer : 공간 예약 -> 물건 넣고 -> 공간 사용
- Consumer : 물건 있니 -> 물건 빼고 -> 공간 비워

## Reader-Writer Problem
- Reader : 읽는다. N명 동시 접근 가능
- Writer : 쓴다. 상호 배제 필요



