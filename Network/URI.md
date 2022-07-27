# URI? URL? URN?
![](./Image/URI%26URL%26URN.png)

## URI (Uniform Resource Identifier)
> ### 인터넷 자원을 나타내는 고유 식별자다.
> - Uniform : 리소스를 식별하는 통일된 방식이다.
> - Resource : 자원, URI로 식별할 수 있는 모든 것이다. (제한 없음)
> - Identifier : 다른 항목과 구분하는데 필요한 정보이다.

### 문법
```
scheme://[userinfo@]host[:port][/path][?query][#fragment]
ex) https://www.google.com:443/search?q=hello&hl=ko
```

- **scheme** : 주로 프로토콜을 사용한다.
- **userinfo** : URL에 사용자 정보를 포함해서 인증할 수 있지만, 거의 사용하지 않는다.
- **host** : 호스트명이 들어가는 곳으로, 도메인명 또는 IP 주소를 직접 사용 가능하다.
- **port** : 접속 포트를 나타내는데 생략 가능하다.
- **path** : 리소스 경로로, 계층적인 구조이다.
- **query** : key=value 형태로 사용하며, `&` 로 추가 가능하다.
- **fragment** : html 내부 북마크 등에 사용하며 서버에 전송하는 정보는 아니다.

## URL (Uniform Resource Locator)
> ### 리소스가 있는 위치를 지정한다.
> - 일반적으로 사이트 도메인을 의미한다.
> - 웹 뿐만 아니라 컴퓨터 네트워크 상의 자원은 모두 표현할 수 있다.

## URN (Uniform Resource Name)
> ### 리소스에 이름을 부여한다.
> - 프로토콜을 포함하지 않는다.
> - 해당 자원의 이름을 의미한다.

## URL과 URN의 특징 비교
- 위치는 변할 수 있지만 이름이 변하진 않는다.
- URL은 해당 자원이 이동한 경우 URL이 더 이상 유효하게 동작하지 않지만, URN은 리소스를 이동시키더라도 문제 없이 동작한다.
- URN 이름만으로 실제 리소스를 찾을 수 있는 방법이 보편화 되지 않아 거의 사용되지 않는다.

---

[^1] https://www.inflearn.com/course/http-%EC%9B%B9-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC/dashboard<br>
