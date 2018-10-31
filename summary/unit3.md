# Unit 3 Summary - 판다스 데이터프레임과 시리즈

* Series() 메소드를 이용하여 시리즈 생성 가능

``` python
s = pd.Series(['banana', 42])
```

* Series() 메소드의 index 속성을 이용하여 인덱스 이름을 지정 가능

``` python
s = pd.Series(['Xsolute', 'Highschool Student'], index=['Person', 'Who'])
```

* 데이터프레임 역시 Series()처럼 DataFrame()을 이용하면 됨

``` python
dataframe = pd.DataFrame()({'foo': ['a', 'b'], 'bar': [1, 2]})
```

* columns 인자를 이용해서 열 순서를 변경 가능

``` python
scientists = pd.DataFrame({
    data={'Name': ['a', 'b'],
          'No': [1, 2],
          'Born': ['810301', '410922']
          'Died': ['110101', '450814']
          'Age': [30, 4]},
    index=['A', 'B'],
    columns=['Name', 'No', 'Born', 'Age', 'Died']
})
```

* 순서가 보장된 딕셔너리를 전달하기 위해서는 OrderedDict를 사용

``` python
from collections import OrderedDict
```

* 데이터프레임에서 시리즈를 선택할 때:

``` python
series = dataframe.loc['Foo']
```

* index 속성: 시리즈의 인덱스가 들어있음

``` python
series.index
# 'Name', 'No', 'Age'
series.index[0]
# 'Name'
```

* values 속성: 시리즈의 데이터가 들어있음

``` python
series.values
# 'Xsolute', '2417', '18'
```

* keys 메소드: 시리즈의 인덱스 반환 (index 속성과 같음)

``` python
series.keys()
# 'Name', 'No', 'Age'
series.keys()[0]
# 'Name'
```

* 시리즈의 mean, min, max, std 메소드

``` python
ages = dataframe['Age']
ages.mean() # ages의 평균값 출력
ages.min() # ages의 최소값 출력
ages.max() # ages의 최대값 출력
ages.std() # ages의 표준편차 출력
```
