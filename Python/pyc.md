# *.pyc
> ### 컴파일 된 바이트 코드이다.
> - *.py 를 읽어서 실행시킬 때 자동으로 생성되는 파일이다.

## python은 인터프리터 언어라고 들었는데 왜 바이트 코드로 컴파일할까
파이썬 가상 머신(VM)은 컴파일러와 인터프리터가 있다. 하지만 인터프리터는 .py에 적힌 소스 코드를 곧바로 번역할 수 없어서, 인터프리터가 번역할 수 있는 byte 코드로 변환되어야 한다.

### interpret vs compile
`interpret` 은 코드 한 줄씩 읽어 해석해주는 즉 동시 통역해주는 방식이고, `compile` 은 한 번에 모든 코드를 한꺼번에 바꿔주는 방식이다.

## python은 왜 바이트 코드로 컴파일 된 파일을 저장할까
파이썬은 기존 인터프리터 작동 방법과는 조금 다르다. 파이썬은 *.py 파일을 실행시킬 때 아래와 같은 두 단계를 가진다.

```
1. *.py를 Python Virtual Machine 이 이해할 수 있는 바이트 코드 형태로 컴파일 한다.
2. 컴파일 된 바이트 코드를 PVM이 단계 별로 실행한다.
```

컴파일러든 인터프리터든 소스 코드를 VM(혹은 CPU 등)이 이해할 수 있는 형태로 번역하는 과정이 필요하다. 하지만 소스 코드를 기계가 이해할 수 있는 형태로 번역하는 과정이 오래 걸린다. 그래서 나온게 1번이 끝나고 나면 결과를 임시 파일(*.pyc)로 저장해두고, 다음부터는 1번은 생략하고 바로 2번을 수행하자는 방법이다.

## *.pyc 파일이 만들어지고 나서 .py 파일을 수정했을 때 .pyc 파일은 업데이트가 될까
*.py 파일을 만들고 최초 실행했을 때 *.pyc 파일이 생길 것이다. 근데 이후에 *.py 파일을 바꾸고 다시 실행하게 되면 *pyc 파일이 존재할 땐 바로 2번으로 간다고 했으니까 수정된 내용은 적용이 안되는거 아닐까 라는 고민이 들었다. 다행히 파이썬은 이런 상황을 대비하여 *.py와 *.pyc 파일의 최근 수정 시간을 확인하고 만약 *.py가 더 최신이라면 *.pyc를 새로 생성한다.

---

[^1] https://stackoverflow.com/questions/2998215/if-python-is-interpreted-what-are-pyc-files<br>
[^2] https://stackoverflow.com/questions/11433579/what-are-motivations-behind-compiling-to-byte-code<br>
[^3] https://stackoverflow.com/questions/8822335/what-do-the-python-file-extensions-pyc-pyd-pyo-stand-for