# Design Pattern
- 개발 과정에서 공통된 문제들을 해결하는데에 쓰이는 형식화 된 가장 좋은 관행이다.
- 프로그램 개발 시에 자주 부닥치는 애로 상황에 대한 일반적이고 재사용 가능한 추상화된 해결책

##  Singleton Pattern
- 한 프로세스에서 하나의 객체만이 필요한 경우
- ex) Setting이 프로그램 전체에 동일하게 유지되어야 하는 경우(ex. dark mode)
- 생성자를 Private으로 하여 외부에서 생성하지 못하게 한다.
- Static 변수 활용
- lazy loading?
- Multi Thread에서 유의해야한다.

## Strategy Pattern
- 동일한 상황에서도 서로 다른 행동이 가능하도록 하는 패턴. (게임에서 다양한 패턴을 사용하는 Npc)

## State Pattern
- 동일한 행동에 대해 상태에 따라 다르게 동작하도록 하는 패턴(리모컨 전원버튼. 터치할 때마다 색이 바뀌는 LED)

## MVC Pattern
- 역할을 분리하여 유지 보수 확장에 용이한 패턴 (React, Django)
- 각 요소의 독립적인 프로그래밍 가능
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
    2. Model과 View를 제어하고 User와 연결하는 다리 역할
