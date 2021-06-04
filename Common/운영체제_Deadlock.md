# Deadlock
- Process가 발생 가능성이 없는 이벤트를 기다리는 상태
- Starvation인 ready상태에서 일어나는 반면, Deadlock은 asleep상태에서 일어난다.

## 자원의 분류
- Preemptible Resources
    - 선점 당한 후 돌아와도 문제 없음
    - Processor, Memory 등
- Non-Preemptible Resources
    - 선점 당하면 문제가 생길 수 있음
    - Disk drive 등
- Total Allocation Resources
    - 자원 전체를 프로세스에 할당
    - Single-core Processor, Disk drive 등
- Partitioned Allocation Resources
    - 하나의 자원을 여러 조각으로 나눠, 여러 프로세스에 할당
    - Memory 등
- Exclusive Allocation Resources
    - 한 순간에 한 프로세스만 사용 가능
    - Processor, Memory, Disk drive 등
- Shared Allocation Resources
    - 여러 프로세스가 동시에 사용 가능
    - Program, Shared Data 등

## Deadlock 발생 필요 조건
1. Exclusive use of Resources
2. Non-preemptible Resources
3. Hold and Wait(자원 하나 hold 하고 다른 자원 요청)
4. Circular Wait

## Deadlock 해결 방법
### Deadlock Prevention
1. Exclusive use of Resources 조건 제거 -> 불가능
2. Non-preemptible Resources -> 불가능
3. Hold and Wait
    - 필요한 자원 한 번에 할당. but 자원 낭비 
4. Circular Wait 
    - 자원들에게 순서 부여
    - 프로세스는 자원의 순서가 증가하는 방향으로만 요청할 수 있도록
    - 여전히 자원 낭비

### Deadlock Avoidance
- 시스템의 상태를 계속 감시
- 시스템이 Deadlock 가능성이 있는 자원 할당 보류
- 항상 Safe State를 유지
- Safe State : 모든 프로세스가 정상 종료 가능한 상태
    - Safe Sequence 존재
- Unsafe State : Deadlock 가능성이 있음
- High Overhead : 항상 시스템을 감시해야 한다.
- 자원 활용 효율이 낮다 : Safe State 유지를 위해
- 실용적이지 않다 : 프로세스, 자원 수가 고정. 필요한 자원의 정확한 예측 필요

1. Banker's Algorithm (Dijkstra)
    - 최대 필요 자원 수와 현재 자원 수, 남은 자원 수를 통해 자원 할당 순서를 정한다.
    - Safe Sequence를 제시한다.
2. Habermann's Algorithm
    - N개의 자원에 대해
    - Safe Sequence를 제시한다.

### Deadlock Detection and Recovery
- 발생하면 그 때 해결하겠다
1. Deadlock Detection
    - 주기적으로 Deadlock 확인
    - Resource Allocation Graph : Edge를 모두 지울 수 있으면 안전
        - Unblocked Process : 필요한 자원을 모두 할당 받을 수 있는 프로세스. 요청 수 <= 남은 자원 수
        - Unblocked Process에 연결된 모든 edge 제거
        - Unblocked Process가 없을 때까지 반복
        - Edge를 다 지울 수 있으면 Deadlock이 아니다
2. Deadlock Recovery
    - Process Termination : 종료할 Process 선택
    1. 비용이 가장 적은 Process 제거
    2. 최소 비용으로 해결 가능한 Process 제거
        - 모든 경우의 수를 봐야함 
    - Resource Preemption : 선점할 자원 선택. 해당 자원을 가지고 있는 프로세스 종료
    - Checkpoint-restart Method : 특정 지점을 Save. 문제 시 복구












