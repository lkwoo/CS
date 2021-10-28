# Design Pattern

##  Singleton Pattern
- 한 프로세스에서 하나의 객체만이 필요한 경우
- ex) Setting(dark mode
- 생성자를 Private으로
- Static 변수 활용
- lazy loading?
- Multi Thread에서 유의해야한다.

## Strategy Pattern
- interface 활용
- 동작들을 모듈화하여 독립적이고 상호 교체 가능하게 만든다
- 특정 작업의 방식, 모드를 바꿔줄 때 (ex. 텍스트, 이미지  옵션 검색)

## State Pattern
- 특정 상태에서 동작을 결정할 때(ex. TV 전원버튼)

## MVC Pattern
- 1979년, Desktop Application을 위한 설계
- 1988년, Small-Talk80 : 현재의 MVC와 비슷
- JSP model 1 : 로직과 출력이 한 페이지에 삽입. 쉬운 코딩. 어려운 유지보수
- JSP model 2(MVC 적용) : 비지니스 로직, 출력 로직 분리. 유지 보수 용이. 분업 용이
- 동작 과정 : User -> Controller -> Model -> Controller -> View -> Controller -> User
- Model : 
  1. 데이터와 행동을 갖는 객체
  2. 비지니스 로직 수행 : 상태 변화 처리, 상태 정보 반환
- View :
  1. 데이터의 시각화
  2. 모델이 처리한 데이터를 받아서 사용
  3. 데이터나 로직이 포함되면 안 됨
- Controller :
  1. 사용자의 요청을 해석하여 처리하고 결과를 반환
  2. Model과 View를 느슨하게 연결
  3. 데이터 흐름 제어
- Why MVC?
  1. 구성요소들으 재사용성 높음
  2. 확장성 증가
  3. 각 요소에 독립적인 프로그래밍
 
