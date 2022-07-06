# HTTP 메시지 [^1]
서버와 클라이언트가 간에 데이터가 교환되는 방식으로 요청(Request)과 응답(Response)가 존재한다.

## 요청(Request), 응답(Response)의 구조
<br>

![](../Image/HttpMessage.png)

### 1. start line (시작 줄)
- 실행되어야 하는 요청 또는 요청 수행에 대한 성공 또는 실패가 기록되어 있다.
- 시작 줄은 항상 한 줄로 끝난다.
- 응답에서는 status line (상태 표시 줄) 이라고도 한다.

### 2. headers
- 요청을 지정하거나, 메시지에 포함된 본문 내용을 설명하는 헤더의 집합이다.

### 3. empty line (빈 줄)
- 요청에 대한 모든 메타 정보가 전송되었다는 것을 알리는 빈 줄이 삽입된다.
- 빈 줄 위로는 헤더이고 아래로는 본문이다.

### 4. body
- 요청과 관련된 내용(HTML 폼 콘텐츠 등)이 옵션으로 들어가거나, 응답과 관련된 문서(document)가 들어간다.
- 본문의 존재 유무 및 크기는 첫 줄과 HTTP 헤더에 명시된다.
<br>

> start line과 headers를 묶어 그냥 요청이나 응답의 헤드라고도 한다.<br>
> payload는 body라고 이야기 한다.

## 요청(Request) 메시지
### 1. start line (시작 줄)
- **`HTTP 메서드`** (Get, Post, Put, Delete, Head, Options)를 사용해 `서버가 수행해야 하는 동작`을 나타낸다.
    > #### [HTTP 메서드 종류](./HTTP_Method.md)
    
- **`요청 타겟`** 은 주로 URL, 프로토콜, 포트 도메인의 절대 경로로 나타낼 수 있으며 RequestContext에 의해 특정지어 진다.
    - 요청 타겟 포맷은 HTTP 메소드에 의해 결정된다.
    <br>
 
    > ### - origin 형식
    > 끝에 `?` 와 쿼리 문자열이 붙는 절대 경로이다. 일반적인 방식으로 `GET`, `POST`, `HEAD`, `OPTIONS` HTTP 메서드와 사용된다.
    > ```
    > POST / HTTP 1.1
    > GET /background.png HTTP/1.0
    > HEAD /test.html?query=alibaba HTTP/1.1
    > OPTIONS /anypage.html HTTP/1.0
    > ```
    > ### - absolute 형식
    > 완전한 URL 형식이다. 프록시에 연결하는 경우 대부분 `GET` 과 함께 사용된다.
    > ```
    > `GET http://developer.mozilla.org/en-US/docs/Web/HTTP/Messages HTTP/1.1`
    > ```
    > ### - authority 형식
    > 도메인 이름 및 포트 번호로 이뤄진 URL 형식이다. HTTP 터널을 함께 구축하는 경우에만 `CONNECT` 와 함께 사용할 수 있다.
    > ```
    > `CONNECT developer.mozilla.org:80 HTTP/1.1`
    > ```
    > ### - asterisk
    > `OPTIONS` 와 함께 `*` 로 서버 전체를 나타낼 때 사용된다.
    > ```
    > `OPTIONS * HTTP/1.1`
    > ```

- **`HTTP 버전`** 을 표시하여 응답 메시지에서 써야 할 HTTP 버전을 알려주는 역할을 한다.

### 2. headers
- HTTP header의 기본 구조를 따른다.
- `대소문자 상관 없는 문자열:헤더에 따라 다른 값` 형식이다.
- 다양한 종류의 header가 있는데 다음과 같은 그룹으로 나눌 수 있다.
    - [General, Request, Entity](./Header.md)

### 3. Body
- 요청의 마지막 부분에 존재한다.
- 모든 요청에 body가 들어가는건 아니다.
    - `GET`, `HEAD`, `DELETE`, `OPTIONS` 처럼 리소스를 받아오는 요청은 보통 body가 필요없다.
- 요청 body는 두 가지로 나뉜다.
    - 단일 리소스 : 헤더 두 개(Content-Type, Content-Length)로 정의된 단일 파일로 구성된다.
    - 다중 리소스 : 여러 파트로 구성된 body에서 각 파트마다 다른 정보를 지닌다. 보통 HTML form과 관련있다.

## 응답(Response) 메시지
### 1. status line (상태 표시 줄)
- **`HTTP 버전`** 을 표시한다.
    - 보통 `HTTP/1.1`
- **`상태 코드`** 를 사용해서 요청의 성공 여부를 나타낸다.
    - [상태 코드 종류](./HTTP_Status_Code.md)
- **`상태 텍스트`** 를 통해 상태 코드의 대한 설명을 한다.
    -  짧고 간결하게 상태 코드에 대한 설명을 글로 HTTP 메시지를 이해하는데 도움을 준다.

### 2. headers
- 다른 헤더와 동일한 구조를 따른다.
- `대소문자 상관 없는 문자열:헤더에 따라 다른 값` 형식이다.
- 다양한 종류의 header가 있는데 다음과 같은 그룹으로 나눌 수 있다.
    - [General, Request, Entity](./Header.md)

### 3. body
- 응답의 마지막 부분에 존재한다.
- 모든 응답에 body가 들어가는건 아니다.
    - 201, 204와 같은 상태 코드를 가지는 응답에는 body가 보통 없다.
- 응답 body는 세 가지로 나뉜다.
    - 이미 길이가 알려진 단일 파일로 구성된 단일 리소스 본문 : 헤더 두 개(Content-Type와 Content-Length)로 정의한다.
    - 길이를 모르는 단일 파일로 구성된 단일 리소스 본문 : Transfer-Encoding가 chunked로 설정되어 있으며, 파일은 chunk로 나뉘어 인코딩 되어 있다.
    - 서로 다른 정보를 담고 있는 멀티파트로 이루어진 다중 리소스 본문 : 이 경우는 상대적으로 위의 두 경우에 비해 보기 힘들다.

---

[^1] https://developer.mozilla.org/ko/docs/Web/HTTP/Messages