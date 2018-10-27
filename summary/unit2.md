# Unit 2 Summary

* pandas: 데이터 분석/시각화 등을 돕는 라이브러리 (import pandas as pd)
* pd.read_csv: tsv/csv 파일을 DataFrame 클래스로 불러오는 메소드

``` python
data = pd.read_csv('../data/data.tsv', sep='\t')
```

* 유용한 함수와 변수들
  * head(): 앞쪽 index를 가진 데이터들을 표시
  * shape: 모양(행, 열 등)을 표시
  * columns: 열의 내용을 표시
  * dtypes: 열의 내용과 자료형 표시
  * info(): 전체적인 정보 표시
* 열 단위로 데이터 추출하기
  * data['열 이름']: '열 이름'의 열 데이터를 추출, '열 이름'에 여러 열을 넣어 다수의 열 데이터를 추출 가능
    * 열 1개만 추출하면 Series, 열 여러개를 추출하면 DataFrame
    * head(), tail()을 이용하여 앞/뒷쪽 index를 가진 데이터를 추출 가능
* 행 단위로 데이터 추출하기
  * loc[인덱스 번호]: **인덱스 번호** 위치에 있는 행 데이터를 추출
    * Tip: loc은 Series, tail은 DataFrame
  * iloc[행 번호]: **행 번호** 위치에 있는 행 데이터를 추출
* 원하는 데이터를 추출하는 여러가지 방법
  * Python 슬라이싱 구문 조합하여 사용
    ``` python
    data.loc[:, ['foo', 'bar']]
    data.iloc[:, [2, 4, -1]]
    ```
  * iloc + range 사용
    ``` python
    range = list(range(5))
    data.iloc[:, range]
    ```
  * 열 지정값에 슬라이싱 사용
    ``` python
    data.iloc[:, 0:6:2]
    ```
  * loc, iloc 자유자재 사용
    ``` python
    data.iloc[[0, 99, 999], [0, 3, 5]]
    data.loc[[0, 99, 999], ['foo', 'bar']]
    ```
  * 그룹화한 데이터의 평균
    * mean() 사용
      ``` python
      data.groupby('year')['life'].mean()
      data.groupby(['year', 'continent'])[['life', 'gdp']].mean()
      ```
  * 그룹화한 데이터의 개수
    * nunique() 사용
      ``` python
      data.groupby('continent')['country'].nunique()
      ```
  * 그래프 제작
    * matplotlib.pyplot 사용
      ``` python
      some_data.plot()
      ```