# 객체 지향 프로그래밍 - OOP
컴퓨터 프로그래밍의 패러다임 중 하나로, 컴퓨터 프로그램을 명령어의 목록으로 보는 시각에서 벗어나 여러 개의 독립된 단위인 객체들의 모임으로 파악하고자 하는 것이다.
각각의 객체는 메시지를 주고 받고, 데이터를 처리할 수 있다.

# OOP가 생긴 배경
초기 컴퓨터 프로그래밍 방식은 절차지향 방식으로 거대해진 소프트웨어를 설계하고 구현하는데 어려움이 생기기 시작했다.
이러한 문제를 해결하기 위해서 프로그램을 함수 단위로 나눠 구조화하는 구조적 프로그래밍 방법이 나타났는데, 데이터 자체를 구조화 하지는 못했다.
그래서 전역 네임 스페이스는 점점 포화 상태가 되는 등의 문제를 해결하기 위해 생긴 방법이 객체 지향이다.
큰 문제를 쪼개는 것이 아니라, 먼저 작은 문제들을 해결할 수있는 객체들을 만든 뒤에 이 객체들을 조합해서 큰 문제를 해결하는 Bottom-up 해결법을 도입한 것이다.

# OOP 장단점
### 장점
객체 지향 프로그래밍을 하면 데이터나 기능에 변화가 생겼을 때, 관련된 객체만 신경을 쓰면 돼서 훨씬 편하다.
코드를 이해하거나 다른 프로그램에서 재사용하기에도 더 수월하고, 전체가 완성되지 않아도 일부 기능만 사용해볼 수도 있어서 테스트에도 더 유리하다.

### 단점
코드를 잘 나누고 설계하는 것이 어렵다. 코드를 작성하기도 전에, 설계부터 많은 노력이 들게 된다.
그래서, 굳이 객체 지향적으로 만들 필요가 없는 경우(규모가 작아서 일을 나누지 않고 혼자 바로 만들때, 데이터를 크게 신경 쓰지 않아도 될 때, 이후에 바뀔 염려가 거의 없을 때)에는 이런 설계 과정 없이 그냥 바로 만들어버리는 게 더 빠르고 효율적일 수 있다.
또 사람이 이해하고 작성하기 편한 방식으로 코드를 나눠두다 보니, 컴퓨터가 이해하는데 시간이 걸려 실행하는 속도가 느려지거나, 저장 공간을 많이 차지하기도 한다.

# OOP의 4가지 특징
### 캡슐화
캡슐화는 속성과 메소드를 하나로 묶는다. 캡슐화된 객체의 세부 내용이 외부에 드러나지 않아서, 변경이 발생할 때 오류의 파급 효과가 적다.
캡슐화된 객체들은 재사용이 용이하다. 객체들 간 메시지를 주고받을 때 각 객체의 세부 내용은 알 필요가 없으므로 인터페이스가 단순해지고, 객체 간 결합도가 낮아진다.

### 추상화
추상화는 인터페이스로 클래스들의 공통적인 특성인 변수, 메소드들을 묶어 표현한다.
인터페이스와 구현을 분리함으로써, 객체가 가진 특성 중 필수 속성만으로 객체를 묘사하고 유사성만을 표현하며 세부적인 디테일은 각 객체에 따라 다르게 구현되도록 할 수 있다.
자바에서는 인터페이스, 추상 클래스, 추상 메소드 정도로 활용할 수 있다.

### 상속
상속은 기존 클래스를 수정하지 않으면서도 이미 정의되어 있는 내용을 확장해서 사용할 수 있는 방법을 제공한다. 상속을 받은 하위 클래스는 상위 클래스의 특성과 기능을 사용할 수 있다.
하위 클래스에서 기능의 일부분을 수정하여 사용할 수 있다.

### 다형성
다형성은 메시지에 의해 객체가 연산을 수행하게 될 때, 하나의 메시지에 대해 각 객체가 가지고 있는 고유한 방법으로 응답할수 있는 능력을 의미한다.
