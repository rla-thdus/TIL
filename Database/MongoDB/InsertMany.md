# MongoDB Insert Many Data
### db.collection.insertMany() [^1]
여러 문서를 컬렉션에 삽입하려면 사용한다.
```shell
$ db.collection.insertMany(
    [<document1>, <document2> ...],
    {
        writeConcern: <document>,
        ordered: <boolean>
    }
)
```
- writeConcern
    - 쓰기 행위를 통제받을 수 있는 레벨을 정하는 옵션이다. 

- ordered
    - 순서가 지정되게 삽입을 해야할 땐 true 값을 주면되고, 아니면 false를 주면된다.
    - 기본값은 true 이다.

### 데이터 여러 개를 넣어줘야 했던 상황
- 컬렉션에서 특정 유저 레코드를 삭제를 시켜줘야 했지만, 그 삭제된 데이터가 완전히 없어지지는 않고 `_archive` 컬렉션에 저장을 해줘야 했다.
- 원래 컬렉션에서 조건에 맞는 문서들을 `_archive` 컬렉션에 넣어줘야 하는데, 먼저 해당 조건에 맞는걸 배열로 반환 받아서 그대로 `_archive` 에 넣어줬다.

```shell
$db.collection.insertMany(
    $db.collection.aggregate([{
        $match:{'Usage.Email':{$in:[이메일 리스트]}}
    }]).toArray()
)
```

---

[^1] https://www.mongodb.com/docs/manual/reference/method/db.collection.insertMany/