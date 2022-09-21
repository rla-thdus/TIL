# pip
파이썬 개발 환경에 패키지를 설치할 때 사용한다.<br>
즉 파이썬으로 작성된 패키들을 관리해주는 시스템으로 우분투의 apt-get, CentOS의 yum, macOS의 brew 같은 존재이다.

파이썬 3.4 버전 이후에는 기본적으로 포함되어 있기 때문에 최신 버전 파이썬을 사용할 경우에는 별도로 설치할 필요가 없다.

## pip list
현재 설치된 패키지 리스트를 볼 수 있는 명령어다. 어떤 패키지가 설치되어 있는지 몇 버전인지를 확인할 수 있다.

```shell
$ pip list
Package    Version
---------- -------
pip        22.0.4
setuptools 58.1.0
wheel      0.37.1
```

## pip install
특정 패키지를 설치할 수 있는 명렁어다.

```shell
$ pip install pandas
```

특정 버전의 패키지를 설치하고 싶을 때는 아래와 같이 하면 된다.
```shell
$ pip install pandas==0.20.3
```

## pip uninstall
pip 를 이용해 설치한 패키지를 삭제할 수 있는 명령어다.
```shell
$ pip uninstall pandas
```

---

[^1] https://pip.pypa.io/en/stable/user_guide/
