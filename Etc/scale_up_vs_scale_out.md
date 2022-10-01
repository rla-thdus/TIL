# Scale-up
쉽게 말하면 기존의 서버를 보다 높은 사양으로 업그레이드하는 방식이다.<br>
하드웨어적인 예를 들면, 성능이나 용량 증강을 목적으로 하나의 서버에 디스크를 추가하거나 CPU나 메모리를 업그레이드시키는 것을 말한다.

이처럼 하나의 서버의 능력을 증강하기 때문에 수직 스케일링(vertical scaling)이라고도 한다.

소프트웨어적인 예로는 AWS의 EC2 인스턴스 사양을 micro에서 small, small에서 medium 등으로 높이는 것으로 생각하면 된다.

# Scale-out
장비를 추가해서 확장하는 방식이다.

기존 서버만으로 용량이나 성능의 한계에 도달했을 때, 비슷한 사양의 서버를 추가로 연결해 처리할 수 있는 데이터 용량이 증가할 뿐만 아니라<br>
기존 서버의 부하를 분담해 성능 향상의 효과를 기대할 수 있다.

서버를 추가로 확장하기 때문에 수평 스케일링(horizontal scaling)이라고도 한다.

클라우드 서비스에서는 자원 사용량을 모니터링하여 자동으로 서버를 증설(Scale Out)하는 Auto Scaling 기능도 있다.

---

[^1] https://stackoverflow.com/questions/50304076/scale-up-vs-scale-out