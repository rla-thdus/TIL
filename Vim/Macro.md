# 매크로 사용하는 방법
### 매크로 기록하기
1. vim의 중립 모드에서 **`q`** 를 누른 다음에 매크로 이름으로 사용할 알파벳이나 숫자를 누른다.
    - a-z, 0-9 중 하나로 정하면 된다.
    - **`qz`** 이라고 누르면 **z** 라는 매크로를 기록하기 시작한다.

2. 하단에 **`recording @z`** 이라고 뜨면 매크로 돌릴 작업을 하면 된다.
3. 그리고 기록이 끝나면 다시 중립 모드에서 **`q`** 를 누르면 된다.

### 매크로 재생하기
- 중립 모드에서 **`@z`** 처럼 자신이 등록한 매크로를 사용하면 된다.

- 가장 최근에 사용했던 매크로를 사용하고 싶다면 **`@@`** 을 누르면 된다.

- 여러 번 반복해서 재생하고 싶을 땐 **`[재생할 횟수]@[레지스터]`** 이렇게 사용하면 된다.
    - **`10@z`** 이렇게 하면 **z** 에 저장된 매크로를 10번 재생하라는 뜻이다.

### 레지스터에 저장된 매크로 확인하기
- vim의 중립 모드에서 **`:register`** 라고 입력하면 모든 레지스터에 저장된 값들을 보여준다.

- 특정 레지스터에 저장된 값을 보고 싶다면 **`:register z`** 라고 입력하면 된다.
    - 이렇게 하면 **`z`** 에 입력된 매크로를 확인할 수 있다.

### 파일에 매크로 저장하기
1. 현재 작업 중인 파일을 저장한다. **`w`**

2. ~/.vimrc 파일을 연다. **`e ~/.vimrc`**

3. **`let @[레지스터]='`** 를 적고 insert 모드에서 **`ctrl+R ctrl+R [저장할 매크로]`** 를 하면 해당 매크로에 저장된 내용이 입력된다.

4. 입력이 됐으면 **`'`** 닫고, 저장하고 나간다.