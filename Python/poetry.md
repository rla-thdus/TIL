# poetry
프로젝트의 의존성를 선언, 관리, 설치하여 어디서나 프로젝트가 작동하도록 도와주는 툴이다.<br>
pip와 다르게 `.toml` , `.lock` 파일을 생성해 의존성를 관리한다.

### .toml
프로젝트 의존성의 메타 데이터를 저장한다. 프로젝트와 의존성 간의 충돌을 해결해 준다.

### .lock
설치된 패키지들의 버전, 해쉬를 저장한다. 프로젝트의 의존성을 다른 환경에서도 유지할 수 있게 도와준다.

## 명령어 사용법
```python
# 새로운 프로젝트 만들기
$ poetry new [프로젝트 이름]

# 이미 존재하는 프로젝트에 poetry 사용하기
$ poetry init

# .toml 파일을 이용한 패키지 설치하기
$ poetry install

# 의존성 추가하기
$ poetry add [추가할 패키지]

# 의존성 삭제하기
$ poetry remove [삭제할 패키지]

# 의존성 업데이트
$ poetry update # poetry.lock 파일을 삭제하고 다시 poetry install 하는 것과 같다.
```

# pip랑 다른 점
### 의존성 해결
내 프로젝트에서 패키지 1, 2가 필요한데, 패키지 2는 패키지 1의 버전이 2.0 이상이여야 한다. 이때 pip로 설치하면 패키지 1을 1.0 버전으로 설치한다고 해도 아무런 문제가 없다.
하지만 poetry는 버전 관련 정보를 확인하고 특정 버전 이상이 아닐 경우에는 아예 설치가 되지 않는다.

### 의존성 잠금
pip는 .lock 파일이 없고 직접 requirements.txt를 작성해야 한다.<br>
반면 poetry는 .lock 파일과 .toml 파일을 자동으로 생성 및 업데이트해 준다.

### 가상 환경
pip는 전역에 패키지를 설치하기 때문에 다른 환경에서의 버전 관리가 불가능하다.
그래서 미니콘다나 virtualenv 같은 툴이 추가적으로 필요하게 된다. 그렇게 되면 따로 놀게될 가능성이 크다.
반면 poetry는 가상 환경 여부를 확인하고 기존 환경, 혹은 새로 만들어 설치하는 등 자동으로 관리해 준다.

---

[^1] https://python-poetry.org/docs/<br>
[^2] https://unbiased-coder.com/python-poetry-vs-pip/<br>
[^3] https://stackoverflow.com/questions/58218592/feature-comparison-between-npm-pip-pipenv-and-poetry-package-managers
