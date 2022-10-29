# Django rest framework
Django 안에서 restful api를 쉽게 만들도록 도와주는 오픈소스 라이브러리이다.

# DRF 사용하는 이유
Django만을 사용할 때는 DB에서 데이터를 꺼내오면 Queryset의 형태로 데이터가 주어진다.
이 경우, 프론트까지 함께 개발하는 경우에는 크게 상관이 없지만 프론트를 별도로 개발하거나, React 혹은 다른 프론트에서도 이용하는 API의 경우에는 Queryset 형태를 피해야 한다.

이 때 rest_framework를 사용하게 되면, view와 model 사이에 serializer라는 것을 사용하게 된다.
View에서 Serializer를 가져와서 사용하게 되면 Model에서 꺼낸 데이터를 Queryset의 형태가 아니라 json/xml 형태로 받아올 수 있다.
이렇게 Django과 DRF를 함께 사용하면 Python으로 만든 백엔드를 다른 프론트엔드에서도 사용할 수 있게 된다.

# Django vs DRF
### 공통점
- 둘 다 파이썬 기반의 웹 프레임워크이다.

### 차이
- Django는 서버와 클라이언트 사이에 html, css, js를 주고 받는다.
- DRF는 서버와 클라이언트 사이에 xml, json 형식의 데이터로 상태를 표시하며 주고 받는다.란
