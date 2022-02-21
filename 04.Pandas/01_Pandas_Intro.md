# Pandas Intro
DataFrame 을 주로 다루기 위한 라이브러리로 데이터 핸들링 작업을 빠르게 할 수 있습니다.<BR>
[Cheat sheet](https://pandas.pydata.org/Pandas_Cheat_Sheet.pdf)<BR>
참고. [예제로 배우는 파이썬 프로그래밍](http://pythonstudy.xyz/python/article/408-pandas-%EB%8D%B0%EC%9D%B4%ED%83%80-%EB%B6%84%EC%84%9D)

## Install
pip 를 이용해 인스톨 가능합니다. Colab 에선 이미 설치되어 지원하기 때문에 생략해도 됩니다.


```python
# !pip install pandas
```

## Basic usage

### Import
보통 pd 로 많이 사용합니다.


```python
import pandas as pd
```

version 확인


```python
pd.__version__
```

### setting
Jupyter 에서 줄 제한을 늘리는 방법


```python
pd.set_option('display.max_rows',80)
```

### Data 형
Pandas 는 크게 3가지 자료형을 제공합니다.<br>
출처. [dooo.park Pandas](https://dooopark.tistory.com/29)

#### Series
1차원 자료구조로 배열/리스트와 같은 일련의 시퀀스 데이타를 받아들이는데, 별도의 인덱스 레이블을 지정하지 않으면 자동적으로 0부터 시작되는 디폴트 정수 인덱스를 사용합니다.


```python
data = [1, 3, 5, 7, 9]
s = pd.Series(data)
s
```


```python
s[0]
```

#### DataFrame
2차원 자료구조로 행과 열이 있는 테이블 데이타(Tabular Data)를 받아들이는데 쓰입니다.


```python
data = {
    'year': [2016, 2017, 2018],
    'GDP rate': [2.8, 3.1, 3.0],
    'GDP': ['1.637M', '1.73M', '1.83M']
}
df = pd.DataFrame(data)
df
```


```python
df['year']
```


```python
df [df['year'] > 2016]
```

#### Panel
3차원 자료구조로
- Axis 0 (items) == DataFrame
- Axis 1 (major_axis) == DataFrame 의 행
- Axis 2 (minor_axis) == DataFrame 의 열

의 3개의 축을 가지고 있습니다.


참고사항. Panel 구조는 더이상 지원하지 않습니다.<BR>
3차원 자료구조를 이용하는 것은 to_frame()을 통해 DataFrame의 MultiIndex를 사용하거나 xarray 패키지를 사용하는 것을 권합니다. pandas는 이 변환을 자동화하기 위해 to_xarray() 메서드를 제공합니다.


출처. [pandas what's new in 0.23.0](https://pandas.pydata.org/docs/whatsnew/v0.23.0.html?highlight=panel#deprecate-panel)<BR>


### File 데이터 불러오기

WEB 상에 있는 파일을 다운로드하기


```python
!wget https://github.com/Finfra/TensorflowStudyExample/raw/master/data/example.csv
!wget https://github.com/Finfra/TensorflowStudyExample/raw/master/data/example.xlsx
```

#### CSV 파일 로드


```python
df = pd.read_csv("./example.csv")
df
```

해당 내용을 꺼내볼 수도 있다.


```python
df['a'][0]
```

#### EXCEL 파일 로드


```python
df = pd.read_excel("./example.xlsx")
df
```

조건에 해당하는 값만 가져오는 것도 가능하다.


```python
df[ df['e'] == 5]
```

#### HTML TABLE 로드
출처. [Myzz's pandas](https://mizykk.tistory.com/40)

HTML 내용중에 테이블 내용을 각각 가져온다.


```python
table = pd.read_html('https://mizykk.tistory.com/39', header=0, encoding='utf-8')
table
```

가져온 데이터 중에 원하는 테이블만 보기


```python
table[1]
```

원하는 테이블 내용만 가져오기


```python
table2 = pd.read_html('https://mizykk.tistory.com/39', match = '국가', header=0, encoding='utf-8')
table2
```

### 데이터를 File로 저장하기

#### CSV 파일 저장

Dumi data 만들기


```python
data = {
    'year': [2016, 2017, 2018],
    'GDP rate': [2.8, 3.1, 3.0],
    'GDP': ['1.637M', '1.73M', '1.83M']
}
df = pd.DataFrame(data)
df
```

저장하기


```python
df.to_csv('./csvsave.csv')
!ls
```

저장된 파일 가져오기


```python
df2 = pd.read_csv('./csvsave.csv')
df2
```

저장하기 전 데이터와 같아지게 Unnamed: 0 컬럼 지우기


```python
df2 = df2.drop('Unnamed: 0',axis=1)
df2
```
