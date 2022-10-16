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