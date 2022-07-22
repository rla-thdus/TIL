## MongoDB Update Data
### db.collection.updateMany() [^1]
지정된 필터와 일치하는 모든 문서를 업데이트 하려면 사용한다.

```shell
$ db.collection.updateMany(<filter>, <update>)
```

### 데이터를 업데이트 해야 했던 상황
- 작년 중순이 되기 전의 데이터들엔 target 값이 존재하지 않고, 그 이후의 데이터들은 target값이 존재한다.
- target 값이 존재하지 않는 데이터에만 target 값을 넣어줘야 하는데, 어떤 target 값을 넣을지는 존재하는 Dummy.Model의 데이터를 바탕으로 정한다.

```shell
# target 값이 존재하지 않으면서 model이 pro인 것만 target 값으로 adult를 준다.
$ db.collection.updateMany(
    {
        'Custom.TrainCourse.Target': {$exists: false},
        'Dummy.Model': 'pro'
    },
    {
        $set: {'Custom.TrainCourse.Target': 'adult'}
    }
)

# target 값이 존재하지 않으면서 model이 Baby인 것만 target 값으로 infant를 준다.
$ db.collection.updateMany(
    {
        'Custom.TrainCourse.Target': {$exists: false},
        'Dummy.Model': 'Baby'
    },
    {
        $set: {'Custom.TrainCourse.Target': 'infant'}
    }
)
```


---

[^1] https://www.mongodb.com/docs/manual/reference/method/db.collection.updateMany/#mongodb-method-db.collection.updateMany<br>
[^2] https://www.mongodb.com/docs/mongodb-shell/crud/update/
