# Rest
자원을 이름으로 구분하여 해당 자원의 상태를 주고 받는 모든 것을 의미한다.

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
- 자원에 대한 행위 : HTTP Method
- 자원에 대한 행위의 내용 : HTTP Message Pay Load (HTTP 요청 보낼 때, 포함되는 데이터를 의미)

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