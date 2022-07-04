# Header [^1]
> ### HTTP Header 는 클라이언트와 서버가 요청 또는 응답으로 부가적인 정보를 전송할 수 있도록 한다.
> 
> 부가적인 정보라고 하면 압축, 인증, 캐싱, message body의 내용 및 크기 등이 있다.

## Header 종류
### General Header [^2]
요청과 응답에 모두 사용되지만 body에서 보내는 데이터와는 관련이 없는 헤더이다.

#### 1. date
- HTTP Message가 만들어진 날짜와 시간을 포함한다.
- Greenwich 표준시. HTTP에서 날짜는 항상 지역 시간이 아닌 GMT로 표현됩니다.

```
date: Mon, 04 Jul 2022 10:55:54 GMT
```

#### 2. connection
- 응답이 전송되고 난 후 네트워크 접속을 유지할지 말지를 제어한다.
- close와 Keep-Alive가 있다.
    - close : 메시지 공유 후 TCP 연결 종료한다.
    - Keep-Alive : 메시지 공유 후 TCP 연결 유지한다.

```
connection: close
connection: Keep-Alive
```

#### 3. cache-control
- 요청과 응답 내의 캐싱 체제를 위한 지시를 정하기 위해 사용된다.
- 요청에서 사용되는 것과 응답에서 사용되는 것이 다르다.

    |요청|응답|
    |---|---|
    |max-age=\<seconds\>|max-age=\<seconds\>|
    |max-stale[\=\<seconds\>]|public|
    |min-fresh=\<seconds\>|private|
    |no-cache|no-cache|
    |no-store|no-store|
    |no-transform|no-transform|
    |only-if-cached|proxy-revalidate|
    ||s-maxage=\<seconds\>|
    ||must-revalidate|

- 캐시 능력

```
public
응답이 어떤 캐시에 의해서든 캐싱된다는 것을 나타낸다.

private
응답이 단일 사용자를 위한 것이며 공유 캐시에 의해 저장되지 않아야 한다는 것을 나타낸다.

no-cache
캐시된 복사본을 사용자에게 보여주기 전에, 재검증을 위한 요청을 서버에 보내도록 강제한다.

only-if-cached
새로운 캐시를 내려받지 않음을 나타낸다.
```

### Request Header [^3]
HTTP 요청에서 사용되지만 request context와는 관련이 없는 헤더이다.


### Response Header [^4]
위치 또는 서버의 정보(이름, 버전)와 같이 응답에 대한 부가적인 정보를 갖는 헤더이다.

### Entity Header [^5]
컨텐츠 길이나 MIME 타입과 같이 Entity Body에 대한 자세한 정보를 포함하는 헤더이다.

---

[^1] https://developer.mozilla.org/ko/docs/Web/HTTP/Headers<br>
[^2] https://developer.mozilla.org/ko/docs/Glossary/General_header<br>
[^3] https://developer.mozilla.org/ko/docs/Glossary/Request_header<br>
[^4] https://developer.mozilla.org/ko/docs/Glossary/Response_header<br>
[^5] https://developer.mozilla.org/ko/docs/Glossary/Entity_header