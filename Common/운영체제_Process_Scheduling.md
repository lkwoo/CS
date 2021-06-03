# Process Scheduling
## Process Scheduling 목적
- 한정된 자원, 여러 개의 프로세스. 자원을 할당할 프로세스를 선택해야 한다.
- 시스템의 성능(Performance) 향상
- 대표적인 성능 지표
    - 응답시간(Response Time) : 작업 요청으로부터 응답을 받을 때까지의 시간
        - 대화형 시스템, Real-Time 시스템
    - 작업 처리량(Throughput) : 단위 시간 동안 완료된 작업의 수
        - 일괄 처리 시스템
    - 자원 활용도(Resource Utilization) : 주어진 시간 동안 자원이 활용된 시간
        - 비싼 장비 활용
- 목적에 맞는 지표를 고려해 스케줄링 해야한다.

## Scheduling Criteria
- 프로세스의 특성 : I/O
- 시스템 특성 : interactive or batch

## Scheduling Level
### Long-Term Scheduling
- Job Scheduling : 커널에 등록할 작업 결정
- 다중프로그래밍 정도 조절 : 시스템 내의 프로세스 수 조절
- I/O Bounded와 Compute-Bounded 프로세스들을 잘 섞어서 선택
- 시분할 시스템에서는 모든 작업을 시스템에 등록 : Long-Term 에서는 취급 안해

### Mid-Term Scheduling
- Memory Allocation 결정

### Short-Term Scheduling
- Process Scheduling : Processor에 할당할 Process를 결정
- 가장 빈번하게 발생
- 매우 빨라야 한다

### Scheduling Policy
- 선점 vs 비선점
    - Non-Preemptive
        - 할당 받은 자원을 스스로 반납할 때까지 사용
        - Context Switching Overhead가 적음
        - 평균 응답시간 증가
    - Preemptive
        - 타의에 의해 자원을 뻇길 수 있음 : 할당 시간 종료, 높은 우선순위 등장
        - Context Switching Overhead가 큼
        - 시분할, 실시간 시스템에 적합
- 우선순위
    - Static Priority
        - 프로세스 생성시 결정. 구현 쉬움.
    - Dynamic Priority
        - 상황에 따라 우선순위 변동. 구현 복잡. 유연한 대응

## Scheduling Algorithm
