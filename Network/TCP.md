# TCP (Transmission Control Protocol)
> ### 서버와 클라이언트간에 데이터를 신뢰성 있게 전달하기 위해서 만들어진 프로토콜이다.
> - 데이터가 전달되는 과정에서 유실되거나 순서가 바뀔 수 있는데 TCP는 유실을 찾아내서 교정하고 순서를 재조합할 수 있게 해준다.
> - 전송 계층의 대표적인 연결지향 프로토콜이다.

## TCP 서비스
### 1. 신뢰성 있는, 순서대로 데이터가 간다.
즉, 데이터를 보낸 순서로 받을 수 있다.

### 2. 흐름 제어 - flow control
수신 측에서 받아들일 수 있는 속도에 맞춰서 송신 측의 데이터를 전달한다.

### 3. 혼잡 제어 - congestion control
네트워크 상황에 맞춰서 그 네트워크가 받을 수 있는 능력치만큼 보내준다.

## TCP 구조
![](http://www.ktword.co.kr/img_data/1889_1.JPG)

#### 발신지 포트 (Source Port)
패킷을 송신하는 시스템의 포트 번호이다.

#### 목적지 포트 (Destination Port)
패킷을 수신하는 시스템의 포트 번호이다.

#### 순차 번호 (Sequence Number)
각 세그먼트의 첫 번째 바이트에 부여되는 번호이다.

#### 응답 확인 번호 (Acknowledge Number)
수신하기를 기대하는 다음 바이트 번호이다. (마지막 수신 성공 순서번호 + 1)

#### 헤더 길이 (Header Length)
TCP 헤더의 길이를 나타낸다.

#### TCP 제어 플래그 (TCP Control Flag)
각 필드 흐름 제어, 종료, 데이터 전송 모드용 구성이다.
- URN (긴급 플래그), ACK (응답 플래그), PSH (Push 플래그), RST (강제 연결 종료 플래그), SYN (연결 요청 플래그), FIN (연결 해제 플래그)

#### 윈도우 크기 (Window Size)
수신 윈도우의 보낼 수 있는 데이터의 양을 뜻한다.

#### 검사합 (Checksum)
데이터가 전송 중에 손실되지 않고 원본과 동일한지 검사할 때 사용한다.

#### 긴급 포인터 (Urgent Point)
세그먼트가 긴급 데이터를 포함하고 있을 경우를 알린다.

---

[^1] http://www.kocw.net/home/search/kemView.do?kemId=1169634<br>
[^2] https://www.inflearn.com/course/http-%EC%9B%B9-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC/dashboard<br>
[^3] http://www.ktword.co.kr/test/view/view.php?m_temp1=1889
