# JWT
Json Web Token의 약자로 인증에 필요한 정보들을 암호화 시킨 JSON 토큰을 말한다. JWT 토큰을 HTTP Header에 심어서 서버가 클라이언트를 식별하는 방식이다.
JWT는 JSON 데이터를 Base64 URL-safe Encode 를 통해 인코딩하여 직렬화한 것이며, 토큰 내부에는 위변조 방지를 위해 개인키를 통한 전자서명도 들어있다.
따라서 사용자가 JWT 를 서버로 전송하면 서버는 서명을 검증하는 과정을 거치게 되며 검증이 완료되면 요청한 응답을 돌려준다.

## 구조
`.` 을 구분자를 통해 나눠지는 세 문자열의 조합이다. `,` 을 기준으로 왼쪽부터 Header, Payload, Signature를 의미한다.

### Header
```json
{
  "alg": "HS256",
  "typ": "JWT"
}
```

- alg : 서명 암호화 알고리즘이다.
- type : 토큰 유형을 나타낸다.

### Payload
```json
{
  "key": "value"
}
```

- 서버와 클라이언트가 주고받는 시스템에서 실제로 사용될 정보에 대한 내용이 `key: value` 로 들어있다.
- 정해진 타입은 없으나 대표적으로 Registered, Public, Private로 나뉜다.
  - Registered: 미리 정의 된 클레임이다.
    - iss(issuer, 발행자)
    - exp(expireation time, 만료 시간)
    - sub(subject, 제목)
    - iat(issued At, 발행 시간)
    - jti(JWI ID)
  - Public: 사용자가 정의할 수 있는 클레임 공개용 정보 전달을 위해 사용한다.
  - Private: 해당하는 당사자들 간에 정보를 공유하기 위해 만들어진 사용자 지정 클레임. 외부에 공개되도 상관없지만 해당 유저를 특정할 수 있는 정보를 담는다.

> 💡claim 은 key-value 형식으로 이루어진 한 쌍의 정보를 뜻한다.

### Signature
- 헤더와 페이로드, 서버가 갖고 있는 유일한 키 값을 합친 것을 헤더에서 정의한 알고리즘으로 암호화를 한다.

---

[^1] https://jwt.io/introduction
