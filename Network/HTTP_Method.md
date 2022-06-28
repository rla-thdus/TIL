## HTTP 메서드 종류 [^1]

## HTTP 메소드의 속성
> HTTP 메소드의 속성에는 **`안전`**, **`멱등`**, **`캐시 가능`** 이 있다.

### 안전 (Safe Methods)
- HTTP 메소드를 계속해서 호출해도 **`리소스가 변경되지 않는다`** 는 뜻이다. 
- GET 메소드가 안전하다고 볼 수 있다.

### 멱등 (Idempotent Methods)
- HTTP 메소드를 여러 번 요청해도 의도한 효과는 **`한 번 요청한 것과 같다.`**
- GET, PUT, DELETE는 멱등하다고 볼 수 있지만, POST나 PATCH는 멱등하다고 볼 수 없다.

### 캐시 가능 (Cacheable Methods)
- 캐싱을 해서 데이터를 효율적으로 가져올 수 있다는 뜻이다.
- GET, HEAD, POST, PATCH 메소드는 캐시가 가능하지만 실제로는 GET과 HEAD만 주로 캐싱을 사용한다.

<br>

|HTTP Methods|요청에 body가 존재|응답에 body가 존재|안전|멱등|캐시 가능|
|---|---|---|---|---|---|
|GET|❌|✅|✅|✅|✅|
|HEAD|❌|❌|✅|✅|✅|
|POST|✅|✅|❌|❌|✅|
|PUT|✅|✅|❌|✅|❌|
|DELETE|❌|✅|❌|✅|❌|
|CONNECT|✅|✅|❌|❌|❌|
|OPTIONS|선택 사항|✅|✅|✅|❌|
|TRACE|❌|✅|✅|✅|❌|
|PATCH|✅|✅|❌|❌|✅|

---
[^1] https://developer.mozilla.org/ko/docs/Web/HTTP/Methods
