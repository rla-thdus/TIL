# Serializer
데이터를 직렬화할 수 있게 도와주는 변환기이다. 즉, 쿼리셋 및 모델 인스턴스와 같은 복잡한 데이터를 Python 데이터 타입으로 변환한 다음 JSON, XML 또는 다른 콘텐츠 유형으로 쉽게 변환해주는 어댑터다.
DRF serializer에는 `Serializer`, `BaseSerializer`, `LitSerializer`, `ModelSerializer`, `HyperlinkedModelSerializer` 가 있다.

# ListSerializer
한 번에 여러 개체를 직렬화하고 유효성을 검사하기 위한 동작을 제공한다.
일반적으로 ListSerializer를 직접 사용할 필요는 없지만 직렬 변환기를 인스턴스화할 때는 `many=True` 를 전달해야 한다.
serializer가 인스턴스화되고 `many=True`가 전달되면 ListSerializer 인스턴스가 생성된다.

# ModelSerializer
serializer를 만들 때 필드를 하나하나 정의해야 했다. 이는 마치 모델을 한 번더 작성하는 듯한 번거로움이 있었다. 이 문제를 해결해주는 것이 바로 `ModelSerializer` 다.

### 제공하는 기능
- 의존하고 있는 모델에 기반해서 자동으로 serializer 필드를 만든다.
- serializer를 위한 validation을 제공한다.
- `.create()`, `.update()` 함수를 기본으로 제공해서 다시 만들 필요가 없다.

```python
class CarSerializer(serializers.ModelSerializer):
    class Meta:
        model = Car
        fields = '__all__'
```
