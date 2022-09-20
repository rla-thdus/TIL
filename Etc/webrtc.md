# WebRTC
Web Real-Time Communication 의 약자로 웹 브라우저 간에 플러그인의 도움 없이 서로 통신할 수 있다.<br>
웹 또는 앱에서 별도의 소프트웨어나 플러그인 없이 음성, 영상, 텍스트 같은 데이터를 브라우저끼리 주고 받을 수 있게 해주는 기술이다.

gather town, google meet 등과 같이 소프트웨어 설치 없이 웹 브라우저만 있으면 화상 회의를 가능하게 해주는 기술이다.

# WebRTC 통신 방식
### p2p (peer to peer)
두 단말이 서로 1:1 통신하는 방식이다.

### MCU, SFU
대규모 서비스를 구축할 때 사용하는 방식으로 중앙 서버를 둬서 트래픽을 중계하게 한다.

# WebRTC 통신 과정
1. 시그널링 통해 통신할 peer 간 네트워크 정보, capability 정보, 세션 수립 등을 교환한다.
2. WebRTC 사용해서 연결을 맺고, peer 기기에서 데이터를 가져와 교환한다.

# P2P로 클라이언트끼리 통신하는데 서버가 필요한 이유

# 실시간으로 통신할 수 있는 이유



---

[^1] https://developer.mozilla.org/ko/docs/Web/API/WebRTC_API<br>
[^2] https://codelabs.developers.google.com/codelabs/webrtc-web/index.html#0
