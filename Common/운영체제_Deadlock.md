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
