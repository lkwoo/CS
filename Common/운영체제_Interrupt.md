# Interrupt
Unexpected external events

## Interrupt의 종류
- I/O Interrupt
- Clock Interrupt
- Console Interrupt
- Program Check Interrupt : 프로그램에 문제가 있으면
- Machine Check Interrupt : 하드웨어에 문제가 있으면
- Inter-Process Interrupt : 다른 프로세스에서 보내는 인터럽트
- System Call Interrupt

## Interrupt Handling Process
1. Interrupt 발생
2. Process 중단
3. Interrupt Handling
    1. Interrupt 발생 장소, 원인 파악
    2. Interrupt를 Service 할지 말지 결정
    3. Service 한다면 -> Interrupt Service Routine 호출

