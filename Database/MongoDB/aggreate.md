# aggreate
### db.collection.aggregate() [^1]
여러 문서를 그룹화하여 연산을 수행한 후 하나의 결과를 반환할 때 사용한다.

```shell
$ db.collection.aggregate(
    [{stage}, ...],
    options
)
```

### aggregation framework pipeline 주요 명령 sql과 비교
|SQL|MongoDB|
|---|---|
|where|$match|
|group by|$group|
|having|$match|
|select|$project|
|order by|$sort|
|limit|$limit|
|sum()|$sum|
|count|$sum|
|join|$lookup|

### 특정 연산을 수행 후 결과를 받아야 했던 상황
- 특정 컬렉션에서 전달되는 이메일 리스트에 포함되는 값을 가지고 있는 문서들을 결과로 받아야 했다.

```shell
$db.collection.aggregate([{
        $match:{'Usage.Email':{$in:[이메일 리스트]}}
    }]).toArray()
```

---

[^1] https://www.mongodb.com/docs/manual/aggregation/
