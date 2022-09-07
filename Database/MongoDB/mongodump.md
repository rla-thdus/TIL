# mongodump
데이터베이스의 내용을 바이너리 내보내기를 할 수 있게 도와준다.<br>
`mongod` 또는 `mongos` 인스턴스에서 데이터를 내보낼 수 있다.

즉, 독립 실행형, 복제본 세트 및 분할된 클러스터 배포에서 데이터를 내보낼 수 있다.

## 사용법
```shell
mongodump <options> <connection-string>
```

#### e.g. 포트 27017에서 실행되는 로컬 MongoDB 인스턴스에 연결하고 기본 설정을 사용하여 ./backup/20220907로 내보내고 싶다.
```shell
mongodump --host 127.0.0.1 --port 27017 --out ~/backup/20220907
```

---

[^1] https://www.mongodb.com/docs/database-tools/mongodump/<br>
[^2] https://stackoverflow.com/questions/4880874/how-do-i-create-a-mongodb-dump-of-my-database
