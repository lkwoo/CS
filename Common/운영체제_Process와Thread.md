# Process
- 실행중인 프로그램
- 커널에 등록되고 커널의 관리하에 있는 작업
- 프로세스 관리 블록(PCB)을 할당 받은 개체

## Process의 종류
1. System(Kernel) Process
2. User Process
3. 독립 Process
4. 협력 Process

## Resource의 개념
- Kernel의 관리 하에 Process에게 할당/반납되는 수동적 개체
- HW : Processor, Memory, disk Monitor...
- SW : Message, Signal, Files...

## Process Control Block : PCB
- OS가 process 관리에 필요한 정보 저장
- Process 생성 시, 함께 만들어짐
- 관리하는 정보
    1. PID : Process 고유 식별 번호
    2. Scheduling 정보 : Process 우선순위 등과 같은 스케쥴링에 필요한 정보
    3. Process 상태 : 자원 할당 정보 등
    4. Memory 관리 정보 : Page table, segment table 등
    5. I/O 상태 정보 : 입출력 장치, 파일 등에 대한 정보
    6. Context 저장 영역 : Process Register 상태를 저장하는 공간 등
    7. 계정 정보
- PCB는 OS 마다 다를 수 있다.
- PCB 참조 및 갱신속도는 OS의 성능을 결정 짓는 중요한 요소 중 하나

## Process States
1. Created State
    - 작업을 터널에 등록
    - PCB 할당 및 Process 생성
    - Memory 할당 받으면 Ready , 아니면 Suspended Ready
2. Ready State
    - Processor 이외의 모든 자원을 할당 받은 상태
    - Running State가 되는 것을 Dispatch or Schedule이라고 표현
3. Running State
    - Processor와 필요한 자원을 모두 할당 받은 상태
    - Preemption : Running -> Ready. Process Scheduling Time out
    - Block/sleep : I/O 자원 대기
4. Blocked/Asleep State
    - Processor 외의 다른 자원을 기다리는 상태. 자원할당은 System Call에 의해 이루어짐
5. Suspended State
    - Memory를 할당 받지 못한 상태
    - Memory Image를 Swap Device에 저장
6. Terminated/Zombie State
    - Process 작업이 끝난 상태
    - 모든 자원 반납
    - Kernel에 PCB의 일부 정보만 남아 있다.

- Ready Queue
- I/O Queue
- Device Queue

## Context Switching
- Context : 문맥. Process와 관련된 정보의 집합
    - CPU register context : CPU
    - Code, Data, Stack, PCB : Memory
- Context Saving : 현재 프로세스의 Register Context를 저장하는 작업
- Context Restoring : Register Context를 Process로 복구하는 작업
- Context Switching : 실행 중인 Process의 Saving과 앞으로 실행할 Process의 Restoring 작업
- 불필요한 Switching을 줄이는 것이 중요하다 -> Thread

## Thread
- Thread : Process에서 자원을 제외한 제어부만을 나타냄  
- Process(제어정보 sp pc 등, 지역데이터, 스택), Resource(코드, 전역데이터, 힙)
- Light Weight Process
- Processor 활용의 기본 단위
- 구성 요소
    - Thread ID
    - Register Set(PC, SP)
    - Stack(Local Data)
- 제어 요소 외의 코드, 데이터 및 자원들은 프로세스 내 다른 스레드들과 공유

1. Thread의 장점
    - 사용자 응답성(Responsiveness) : 일부 스레드의 처리가 지연되어도, 다른 스레드는 작업을 계속 처리 가능
    - 자원공유(Resource Sharing) : 자원을 공유해서 효율성 증가. Kernel 개입 최소화
    - 경제성(Economy) : Process의 생성, Context Switching에 비해 효율적
    - 멀치 프로세서(Multi-Processor)활용 : 병렬처리를 통해 성능 향상 
2. 사용자 수준 스레드(User Thread)
    - 사용자 영역의 스레드 라이브러리로 구현됨
    - 스레드의 생성, 스케줄링 등
    - POSIX Threads, Win32 Threads, JAVA Thread API 등\
    - 커널은 Thread의 존재를 모름, Process가 Block 되면 모든 Thread 대기
3. Kernel 수준 스레드(Kernel Thread)
    - OS가 직접 관리
    - Kernel 영역에서 스레드의 생성, 관리 수행. Context Switching 등 Overhead가 큼
    - Kernel이 각 Thread를 개별적으로 관리
- Multi-Thread : 혼합형 N:M. N개의 사용자스레드 M개의 커널스레드. N >= M
 
