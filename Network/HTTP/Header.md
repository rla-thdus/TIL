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

- 만료

```
max-age=<seconds>
캐시가 최신 상태라고 판단할 최대 시간을 지정한다.

s-maxage=<seconds>
max-age 혹은 expires 헤더를 재정의하지만 공유 캐시에만 적용되며 사설 캐시에는 무시된다.

max-stale[=<seconds>]
클라이언트가 시간이 만료된 캐시의 응답을 받아들일지를 나타낸다.

min-fresh=<seconds>
클라이언트가 지정된 시간 동안 최신 상태로 유지되는 응답을 원한다는 것이다.
```

- 재검증

```
must-revalidate
캐시를 사용하기 전에 기존 캐시의 상태를 반드시 확인하며, 만료된 캐시는 사용되어선 안된다.
```

- 기타

```
no-store
어떤 요청도 캐시로 저장하지 않는다.

no-transform
응답에 대해 변형이나 변환이 있으면 안된다.
```

### Request Header [^3]
HTTP 요청에서 사용되지만 request context와는 관련이 없는 헤더이다.

#### 1. accept
- 요청자가 원하는 미디어의 타입 및 우선 순위를 표현한다.
- accept는 부속 속성이 있다. (`accept-*`)

```
accept: application/json, text/plain, */*
-> json > text > all type 순서로 받는다는 표현이다.

accept-language: en-US,en;q=0.5
-> 언어는 en이라는 표현이다. q는 가중치다.

accept-encoding: gzip, deflate, br
-> gzip, deflate, br(Brotli) 등등의 압축 포맷을 받는다는 표현이다.
```

#### 2. user-agent
- 요청자의 소프트웨어 정보를 나타낸다. 
    - 소프트웨어 정보 : OS, 브라우저, 기타 버전 정보

```
user-agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/103.0.0.0 Safari/537.36
```

#### 3. cookie
- 서버에 의해서 이전에 저장된 쿠키를 포함시키는 속성이다.

```
cookie: NNB=5HTAB5CDIDJSE; nx_ssl=16521; ASID=78946516018157006132546546
```

#### 4. refer
- 현재 요청을 보낸 주소의 절대 혹은 부분 주소를 포함한다.

```
referer: https://www.naver.com/

referrer-policy: 얼마나 많은 리퍼러 정보를 포함하는지 알려준다. (오타 내가 낸게 아니라 오타가 스펙이 되었다 한다)
```

### Response Header [^4]
위치 또는 서버의 정보(이름, 버전)와 같이 응답에 대한 부가적인 정보를 갖는 헤더이다.

#### 1. age
- max-age 내에서 캐시가 얼마나 지났는지 초 단위로 표현한다.

```
age: 24
```

#### 2. location
- 리다이렉션할 페이지를 나타낸다.
- 3XX(redirect)나 201(created) 상태 응답과 함께 제공될 때 사용한다.

```
location: https://en.dict.naver.com/#/main
```

#### 3. server
- 서버의 정보를 나타낸다.

```
server: nfront
```

#### 4. set-cookie
- 서버에서 사용자에게 쿠키 정보를 전달한다.

```
set-cookie: JSESSIONID=7D165AD9131K546279Od515632190; Path=/; HttpOnly
```

#### 5. date
- 서버 응답 메시지가 생성된 시간을 나타낸다.

```
date: Wed, 06 Jul 2022 11:26:50 GMT
```

### Entity Header [^5]
컨텐츠 길이나 MIME 타입과 같이 Entity Body에 대한 자세한 정보를 포함하는 헤더이다.

---

[^1] https://developer.mozilla.org/ko/docs/Web/HTTP/Headers<br>
[^2] https://developer.mozilla.org/ko/docs/Glossary/General_header<br>
[^3] https://developer.mozilla.org/ko/docs/Glossary/Request_header<br>
[^4] https://developer.mozilla.org/ko/docs/Glossary/Response_header<br>
[^5] https://developer.mozilla.org/ko/docs/Glossary/Entity_header

