# $exists
```javascript
{field: {$exists: Boolean}}
```
- 특정 필드가 존재하는지 알고 싶을 때 사용한다.
- Boolean 값이 False 면 해당 필드가 존재하지 않는 문서들을 반환하고, True 면 해당 필드가 존재하는 문서들을 반환한다.

### 특정 필드가 존재하고 있는지 확인 후 없으면 넣어줘야 했던 상황
- 특정 필드가 없는지 확인을 하고 없는 문서들에게는 해당 필에 맞는 값을 넣어줘야 했다.

```javascript
db.collection(clientID).updateMany(
    {"email": email, "user_id": {"$exits": false}},
    {"$set": {"user_id": user_id}}
)
```

---

[^1] https://www.mongodb.com/docs/manual/reference/operator/query/exists/
