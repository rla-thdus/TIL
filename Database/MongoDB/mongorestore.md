# mongorestore
`mongodump` 에 의해 생성된 바이너리 데이터베이스 덤프 또는 표준 입력을 `mongod`나 `mongos` 인스턴스에 데이터를 로드한다.

새 데이터베이스를 만들거나 데이터를 추가는 할 수 있지만 업데이트는 할 수 없다.<br>
즉, 기존 문서가 복원 문서와 동일한 `_id` 값을 갖는 경우, 해당 문서를 덮어쓰지 않는다.

## 사용법
```shell
mongorestore <options> <connection-string> <directory or file to restore>
```

#### e.g. backup 디렉토리를 로컬의 mongod에 복원하고 싶다.
```shell
mongorestore ./backup
```

---

[^1] https://www.mongodb.com/docs/database-tools/mongorestore/<br>
[^2] https://www.mongodb.com/docs/manual/core/wiredtiger/#compression
