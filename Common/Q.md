  - 운영체제
 1) OS 무엇이며 핵심 기능은?
    - OS란 컴퓨터의 자원 관리자입니다. 다양한 역할이 있는데 CPU 스케줄링, Process 및 Memory 관리 등 컴퓨터 자원을 관리합니다.
 2) 프로세스와 스레드의 차이점을 Context Switching 관점으로 설명
    - 프로세스는 실행중인 프로그램을 의미합니다. 스레드는 프로세스의 제어부를 말합니다. Light Weight Process라고 부르기도 합니다. 따라서 Context Switching에서 Thread가 더욱 유리합니다. 다만 공유 자원에 대한 처리는 까다롭습니다.
 6) 어떤 경우에 프로세스와 스레드를 사용하는지 예시와 각각의 장단점 설명
    - 공통적으로는 자원의 효율적인 사용으로 성능을 높이는것을 목적으로 합니다. 병렬처리를 통해 더욱 빠르게 작업을 완료할 수 있습니다. 멀티 프로세스는 각 프로세스가 독립적으로 동작하므로 Context Switching의 overhead가 큰 편입니다. 대신 동기회 문제로부터 자유롭습니다. 멀티 스레드는 제어부를 제외한 자원을 공유하기 때문에 Context Switching의 overhead가 적습니다. 다만 Critical Section에서 발생할 수 있는 문제를 대비해야 합니다.
 8) 리눅스를 사용해보았다면, 자주 사용하는 리눅스 명령어
    - 저는 Change Directory나 List Segments 같은 일반적인 명령을 제외하고는 grep 명령을 자주 사용합니다. 폴더와 파일이 많을 때, 원하는 내용의 파일을 빠르게 찾는데 주로 사용합니다. grep -ri "asd" : 재귀적으로 대소문자구분없이
 10) IPC에 대한 설명
    - 프로세스간 통신을 위해 두 가지 방법이 있습니다.
    - 첫 번째는 공유 메모리를 사용하는 방법입니다. 빠르다는 장점이 있지만 Race Condition에 대한 처리는 복잡하다는 단점이 있습니다.
    - 두 번째는 메시지 전달 방법입니다. 커널을 통해 메시지를 주고 받습니다. 구현은 간단하지만 Context Switching이 자주 일어나 속도가 느립니다.
 12) 데드락에 대한 설명과 이를 해결하기 위한 회피책 설명
    - Deadlock은 발생 가능성이 없는 이벤트를 기다리는 상황을 말합니다. 이를 회피책으로는 Banker's 알고리즘이 있습니다. 자원 분배를 했을 때, Safe Sequence가 보장되는 경우에만 자원을 분배합니다. 대신 필요한 자원을 정확히 판단해야 하는 어려움이 있습니다.
 14) 임계 영역이란 무엇인지 설명하고, 세마포어와 뮤텍스의 차이점 설명
    - 임계 영역이란 Race Condition이 발생할 수 있는 영역을 말하는데, 여러 프로세스가 한 자원에 동시에 접근할 경우 문제가 생길 수 있는 영역입니다.
 16) CPU 스케줄링에 정의와 목적 설명
    - 여러 프로세스를 동시에 실행할 때, 각 프로세스에 적절한 자원 분배를 위한 방법입니다. 효율에 초점을 맞춘 방법과 형평성에 초점을 맞춘 방법 등이 있습니다. 전자같은 경우에는 FCFS가 해당이 되고 후자의 경우에는 RR이 해당됩니다. 우선순위에 따라 Q를 만들어 각 Q에 다른 스케줄링을 하고 또 Q간의 이동이 가능한 MFQ 방법도 있습니다.    
 20) 가상 메모리에 대한 정의와 구현 기법 설명
    - 프로그램의 일부만 메모리에 올려 실제 메모리 용량보다 큰 프로그램을 실행할 수 있다.
    - 메모리 공간을 효율적으로 사용할 수 있다.
    - Paging Table을 통해 논리 메모리에서 물리메모리로 매핑
 22) 페이지 교체 알고리즘에 대한 설명
    - 내부 단편화 가능
 24) write back과 write through
    - Write 연산이 생기는 즉시 메모리 업데이트 -> WT
    - Cache에서 Block이 내려갈 때 -> WB
 
 - 데이터 베이스 
 1) DB 무결성과 정합성 설명
 2) DB 무결성의 4가지 설명
 3) DB 제약 조건의 종류와 무결성을 연관 설명
 4) DB 정규화 단계 설명
 5) 데이터 베이스 언어 (DDL, DML, DCL, TCL)에 대한 설명
 6) 뷰 특징과 장단점 설명
 7) 조인 (내부/외부 조인)에 대한 설명
 8) JDBC와 ODBC의 차이점 설명
 9) statement와 preparestatement의 차이점
10) SQL vs NoSQL (https://siyoon210.tistory.com/130)
 
- 웹
 1) GET과 POST의 차이점
 2) session과 cookie 차이점과 사용 용도 설명
 3) HTML과 XML의 차이점과 장단점 설명
 4) MVC 모델이란, 프레임워크란?
 5) Spring Framework에 대한 설명 
 6) JSP와 Servlet의 차이점
 7) JSP와 ASP 그리고 PHP의 차이점
 8) AJAX에 대한 설명
 
 - JAVA
 1) String과 StringBuffer의 차이점
 2) Interface와 Abstract의 차이점
 3) Static의 의미와 선언하지 않은 것과의 차이점
 4) Heap과 Stack에 대한 설명
 5) Call by value와 Call by reference 차이점
 6) Java와 Javascript의 차이점
 
 - 기타
 1) 정렬 알고리즘중 가장 빠른 방식과 느린 방식을 설명와 이유
 2) 탐욕 알고리즘이란?
 3) 객체란?
 4) 이진 탐색 방식을 시퀀스 서치와 비교하여 이점을 설명
 

- 자료구조
 1) Tree란?
 2) Binary Tree란?
 3) Binary Tree에서 Non-leaf와 Leaf 노드 개수의 관계식은?
 4) Heap Tree란?
 5) Heap Tree의 데이터 삭제, 추가 과정을 설명하시오
 6) Tree에서 pre, in ,post order를 설명하시오
 7) B tree란?
 8) B Tree의 데이터 삭제 추가 과정
 9) Array List와 Linked List의 차이점은?
 10) Graph란?
 
 - 알고리즘
 12) Big O란?
 13) Divide and conquer를 사용한 알고리즘 예를 들어보라
 14) Divide and conquer와 Dynamic Programming의 차이점 및 유사점은?
 15) Backtracking과 Branch and Bound의 차이점은? 
 16) Merge/Quick/Heap sort의 best, average, worst 케이스의 시간 복잡도는?
 17) Merge sort와 Quick sort의 차이점과 방식은?
 18) Quick sort와 Bubble sort의 차이점은?
 19) Floyd 알고리즘이란?
 20) Dijkstra 알고리즘이란?
 21) Floyd와 Dijkstra 알고리즘의 차이점과 정의는?
 22) 프림 알고리즘과 크루스컬 알고리즘의 차이 그리고 시간복잡도는?
 23) Knapsack problem과 Traveling Salesman Problem에 대한 설명
 24) P와 NP, NP-Completeness에 대한 설명
 25) 퀵소트와 머지소트를 캐시 히트 율과 연관지어 설명하시오
 26) 객체지향 5원칙
 27) 객체지향 특징
 

 
 - 네트워크와 인프라 
 1) GET과 POST의 차이점
 2) TCP/IP, UDP 프로토콜 설명
 3) MTTR, MTTF, MTBF에 대한 설명
 4) 파티션 테이블이 필요한 이유?
 5) OSI 7 계층을 나눈 이유
 6) TCP 3 hand shaking이란?
 7) L2, L3, L4 차이점
 8) 허브와 스위치의 차이점
 9) 파이썬과 다른 언어의 차이점
 10) 데이터 계층의 PDU는 무엇인가?
 11) 시퀀스 넘버에 대한 역할
 12) 슬라이딩 윈도우의 역할
 13) HTTP 응답코드의 종류를 아는대로 설명
 14) MIME 프로토콜 설명

1. 운영체제/프로세스간 통신과 동기화  
- 큐와 스택 차이  
- critical section 관련 문제  
- producer/consumer 관련 문제  

2. Cache miss  
- Locality에 대한 정의  
- Block size를 늘리면 miss rate가 왜 U자형 그래프 그리는지 설명, block size 크기가 miss penalty에 미치는 영향  
- cache-friendly한 자료구조, T/F 번갈아 나오는 분기에서 branch predictor이 불리한 이유  

3. Pipeline
- Harzard의 종류와 특징
- 각 단계의 특징 

1. big - o

2. struct와 union의 차이

3. Binary search tree
3.1개념
3.2 삽입과 삭제
3.3 편향 트리에서 균형 트리로 만들기

1. 다익스트라 알고리즘
1.1 개념
1.2 O(N^2)의 시간복잡도로 구현하는 다익스트라 알고리즘에서 2차원 배열 채우기 (연결 관계 채우기)
1.3 주어진 빈 칸 코드로 채우기 (최단 거리를 갱신하는 부분)

1. DB Transaction
문제 상황 :
내가 물건을 팔고 네가 물건을 사는데
너의 DB를 업데이트하는데 문제 생겼다.
1.1 트랜잭션의 정의
1.2 트랜잭션 특징	
1.3 주어진 상황에서 DB 측면에서 어떻게 해결하는가?

2. OS deadlock 문제

3. quick sort
3.1 개념 정의
3.2 수도코드
3.3 오름차순 내림차순 O(n^2) 해결방법
