# 트랜 잭션 격리 수준 - Transaction Isolation Level
동시에 여러 트랜잭션이 처리될 때, 특정 트랜잭션이 다른 트랜잭션에서 변경하거나 조회하는 데이터를 볼 수 있도록 허용할지 말지를 결정하는 것이다.

# 격리 수준이 필요한 이유


# Isolation Level 종류
4개의 격리 수준에서 순서대로 뒤로 갈수록 각 트랜잭션 간의 데이터 격리 정도가 높아지며, 동시성이 떨어진다.

### 1. Read Uncommitted - level 0 
- SELECT 문장이 수행되는 동안 해당 데이터에 Shared Lock이 걸리지 않는 계층이다.
- 트랜잭션에 처리중이거나, 아직 커밋되지 않은 데이터를 다른 트랜잭션이 읽는 것을 허용한다

### 2. Read Committed - level 1
- SELECT 문장이 수행되는 동안 해당 데이터에 Shared Lock이 걸리는 계층이다.
- 트랜잭션이 수행되는 동안 다른 트랜잭션이 접근할 수 없어 대기하게 된다.
- 커밋이 이루어진 트랜잭션만 조회 가능하다.
- 대부분의 SQL 서버가 디폴트로 사용하는 격리 레벨이다.

### 3. Repeatable Read - leve 2
- 트랜잭션이 완료될 때까지 SELECT 문장이 사용하는 모든 데이터에 Shared Lock이 걸리는 계층이다.
- 트랜잭션이 범위 내에서 조회한 데이터 내용이 항상 동일함을 보장한다.
- 다른 사용자는 트랜잭션 영역에 해당되는 데이터에 대한 수정 불가능하다.
- MySQL에서 디폴트로 사용하는 격리 레벨이다.

### 4. Serializable - level 3
- 트랜잭션이 완료될 때까지 SELECT 문장이 사용하는 모든 데이터에 Shared Lock이 걸리는 계층이다.
- 가장 엄격한 격리 수준으로 완벽한 읽기 일관성 모드를 제공한다.
- 다른 사용자는 트랜잭션 영역에 해당되는 데이터에 대한 수정 및 입력 불가능하다.
