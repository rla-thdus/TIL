## REST 탄생 배경
HTTP 주요 저자 중 한 사람인 Roy fielding은 그 당시 HTTP 설계의 우수성에 비해 제대로 사용되고 있지 않다고 느껴서 웹의 장점을 최대한 활용할 수 있는 아키텍처로 REST를 발표했다.

# REST
**`Representational State Transfer`** 의 약자이다.
말 그대로 자원을 이름으로 구분하여 해당 자원의 상태를 주고 받는 모든 것을 의미한다.

#### 즉 rest란
- HTTP URI를 통해 자원(Resource)를 명시하고
- HTTP Method(Get, Post, Put, Delete)를 사용해서
- 해당 자원에 대한 CRUD Operation을 적용하는 것이다.

>**CRUD Operation** 은 기본적인 데이터 처리 기능인 Create(생성), Read(읽기), Update(갱신), Delete(삭제)를 묶어서 일컫는 말로 REST에서의 CRUD Operation 동작 예시는 다음과 같다.
>```
>Create : Post (생성)
>Read : Get (조회)
>Update : Put (수정)
>Delete : Delete (삭제)
>```

## REST 구성 요소
- 자원 : URI
- 자원에 대한 행위 : HTTP Method (GET, POST, PUT, DELETE)
- 표현 : 클라이언트와 서버가 데이터를 주고 받는 형태 (json, xml ...)

#### 자원이란
해당 소프트웨어가 관리하는 모든 것을 말한다.

### 왜 REST API를 쓸까?
- 내용을 딱 보면 무엇을 요청하는 것인지 직관적으로 이해할 수 있다.
- HTTP 인프라를 그대로 사용하기 때문에, REST API를 위한 별도의 인프라를 따로 구축하지 않아도 된다.
- 데이터만 주고 받기 때문에 여러 클라이언트가 자유롭고 부담없이 사용할 수 있다.

## REST API 특징
### Client-Server Architecture
Client와 Server로 영역을 분리한다. 유저 인터페이스와 데이터를 저장하는 두 가지를 분리하면 서버가 처리하는 부분이 줄어들고 여러 플랫폼과, 유저 인터페이스로 확장하기가 편하다. 요즘은 하나의 데이터를 웹과 앱 등에서 보여줘야 하기 때문에 이럴 때 REST API가 유용하다.

### Stateless
HTTP가 stateless한 프로토콜이기 때문에 rest 역시 무상태성을 갖는다. 즉, 서비스의 클라이언트가 동작하는 과정에서 생기는 상태 변화에 대해서 서버는 관여하지 않고 오직 클라이언트에서 감당한다. 따라서 서버에 요청을 보낼 때는 서버가 요청을 해결하기 위한 정보들을 포함하고 있어야 한다.

### Self-Discriptiveness
요청 메시지만 보고도 어떤 일을 하는지 쉽게 이해할 수 있는 자체 표현 구조이다.

### Caching
HTTP라는 웹 표준을 그대로 가져다 사용하기 때문에, 웹에서 사용하는 인프라를 그대로 사용할 수 있다. 따라서 HTTP가 가진 캐싱 기능을 사용할 수 있다. HTTP 표준에서는 Last-Modified 태그와 E-tag를 이용하면 캐싱 구현이 가능하다.

### Uniform Interface
URI로 지정한 리소스에 대한 조작을 통일되고 한정적인 인터페이스로 수행하는 아키텍처 스타일을 말한다. 즉 요청을 하는 Client가 플랫폼(Android, Ios, Jsp 등) 에 무관하며, 특정 언어나 기술에 종속받지 않는 특징을 의미한다. 덕분에 Rest API는 HTTP를 사용하는 모든 플랫폼에서 요청 가능하다.

### Hierarchical System
다중 계층으로 구성될 수 있어서 로드 밸런싱, 보안, 암호화와 같은 계층을 추가해서 구조상의 유연성을 둘 수 있다. proxy와 gateway 같은 네트워크 기반의 중간 매체도 사용할 수 있다. 하지만 클라이언트는 서버와 직접 통신하는지, 중간 서버와 통신하는지 알 수 없다.

# REST API URI 규칙 [^1]
#### 1. 소문자를 사용한다.
```
Bad - http://example.com/Restaurants/Seoul
Good - http://example.com/restaurants/seoul
```

#### 2. 언더바 대신 하이픈을 사용한다.
```
Bad - http://example.com/restaurants/seoul/high_rated
Good - http://example.com/restaurants/seoul/high-rated
```

#### 3. URI 마지막에 슬래시를 포함하지 않는다.
```
Bad - http://example.com/restaurants/seoul/
Good - http://example.com/restaurants/seoul
```

#### 4. URI에 작성되는 영어는 복수형으로 작성한다.
```
Bad - http://example.com/restaurant/seoul/2345/menu
Good - http://example.com/restaurants/seoul/2345/menus
```

#### 5. 계층 관계를 나타낼 때는 슬래시를 사용한다.
```
Bad - http://example.com/restaurants/get-seoul
Good - http://example.com/restaurants/seoul
```

#### 6. 파일 확장자는 URI에 포함하지 않는다.
```
Bad - http://example.com/restaurants/seoul/2345/menus/1.png
Good - http://example.com/restaurants/seoul/2345/menus/1
```

# 적용할 예정
회사에서 사용하는 API가 restful 하지 않다고 느껴졌다. post를 무분별하게 사용하는 등의 모습을 보면서 한 번 내가 바꿔보면 좋겠다는 생각에 시도하게 되었다.

```javascript
// restful 하지 않았던 전의 모습
...
router.post('/data', controller.postData)
router.post('/onlyData', controller.postOnlyData)
router.get('/data', controller.getAllData)
router.get('/data/:client_id', controller.getData)
router.delete('/data/:client_id', controller.deleteData)
router.post('/data/:client_id/counts', controller.countsData);
router.post('/data/:client_id/count/cert', controller.certData);
router.post('/data/:client_id/count', controller.countData);
router.post('/search/:client_id', controller.searchData);
router.post('/search/totaleventtime/:client_id', controller.getTotalEventTimeData);
router.post('/search/:client_id/:id', controller.getSpecificData);
router.post('/data/:client_id/download/:from?/:to?', controller.downloadData);
router.get('/qdata/:client_id/:record_id', controller.getQData);
```


[^1] https://dzone.com/articles/7-rules-for-rest-api-uri-design-1

