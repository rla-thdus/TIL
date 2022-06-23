# HTTP
`HTML`과 같은 하이퍼미디어 문서를 전송하기 위한 응용 프로그램 계층 프로토콜이다.<br>
지금은 HTML 뿐만 아니라 거의 모든 것을 HTTP로 전송 가능하다.
<br>

> ### 전송 가능한 리소스
> 
> - HTML, TEXT, IMAGE, 음성, 영상, 파일, JSON, XML(API) 등 거의 모든 형태의 데이터 전송 가능하다.
> - 서버 간에 데이터를 주고 받을 때도 대부분 HTTP를 사용한다.
<br>

## HTTP 특징
### Client-Server
클라이언트가 요청을 위한 연결을 열고 응답을 받을 때 까지 기다리는 Client-Server 모델 구조이다. 

### Stateless protocol
서버의 응답이 클라이언트의 세션 연결 상태와 독립적이다. 즉, 서버에 client의 동작이나 상태 정보를 저장하지 않는다.