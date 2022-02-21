# Pandas Data
Pandas 에서 사용되는 Data Type 에 대해 알아봅니다.

## Import
보통 pd 로 많이 사용합니다.


```python
import pandas as pd
```

version 확인


```python
pd.__version__
```

## Series

Index 와 Value 로 구성되어 Python 의 Dictionary 와 유사한 형태이다.

### 데이터 생성

#### List 로 생성하기


```python
data = pd.Series([1,2,3,4])
data
```

#### Tuple 로 생성하기


```python
data = pd.Series((1,2,3,4))
data
```

#### Array 로 생성하기


```python
import numpy as np
data = pd.Series(np.array([1,2,3,4]))
data
```

#### Dictionary 로 생성하기


```python
data = pd.Series({0 : 1, 1 : 2, 2 : 3, 3 : 4.5})
data
```

#### 여러 자료 형 index 를 넣어 생성하기


```python
data = pd.Series(["abc", 3, 4.5], index=["initial","ea","float"])
data
```

### 데이터 접근

#### Index(키) 값 가져오기


```python
data.index
```

#### Value 값 가져오기


```python
data.values
```

#### 특정 값 접근


```python
data[2]
```

#### Index 명 바꾸기


```python
data.index = ["what", "when", "where"]
data
```

#### index 로 조회하기


```python
data.at["what"]
```


```python
data[["what","where"]]
```

#### 범위로 조회하기


```python
data[0:2]
```


```python
data[-2:]
```

## DataFrame

인덱스가 같은 하나 이상의 Series 가 모여진 데이터형으로 DB 의 Table 과 유사한 형태이다.

### 데이터 생성

#### 데이터 생성예시


```python
pdata = pd.DataFrame([ [1,2],[3,4],[5,6],[7,8] ])
pdata
```

#### Index 와 컬럼명을 지정하여 생성하기


```python
pdata = pd.DataFrame([[90,90,90],[75,90,75],[90,30,90],[45,45,45]], index=["철수","영희","영수","희영"], columns = ["국","영","수"])
pdata
```

### 데이터 접근

#### column 조회


```python
pdata["국"]
```

#### Index 조회


```python
pdata.loc["철수"]
```


```python
pdata.loc[["철수","영희"]]
```


```python
pdata.iloc[0]
```

#### 범위로 조회


```python
pdata.iloc[:2]
```

#### Index 명 바꾸기


```python
pdata.index = ["수철","희영","수영","영희"]
pdata
```


```python
pdata.columns = ["수","영","국"]
pdata
```


```python
pdata["과학"] = [90,75,30,45]
pdata
```


```python

```
