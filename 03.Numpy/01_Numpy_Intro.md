# Numpy Intro
* Numpy 는 다차원 배열을 쉽게 처리하고 효율적으로 사용할 수 있도록 지원하는 파이썬의 패키지로 데이터 구조 외에도 수치 계산을 위해 효율적으로 구현된 기능을 제공합니다.<BR>
데이터 분석을 할 때, [Pandas](https://pandas.pydata.org/) 와 함께 자주 사용하는 도구로 등장합니다.
* Numpy Home : https://numpy.org/doc/stable/user/index.html    

## Install
pip 를 이용해 인스톨 가능합니다. Colab 에선 이미 설치되어 지원하기 때문에 생략해도 됩니다.


```python
# !pip install numpy
```

## Basic Usage

### Import
보통 np 로 줄여서 많이 쓰입니다.


```python
import numpy as np
```

version 확인


```python
np.__version__
```

### data 형 바꿔보기

np array 생성


```python
data = [[1,2],[3,4]]
arr = np.array(data)
arr.shape
```

차원수 확인


```python
arr.ndim
```

reshape 로 바꿔주기


```python
arr2 = arr.reshape((-1))
arr2.shape
```


```python
arr2.ndim
```

### 행렬 만들기

데이터가 비어 있는 행렬 만들기


```python
np.empty((3,3))
```

1 로 채워진 행렬 만들기


```python
np.ones((3,3))
```

0 으로 채워진 행렬 만들기


```python
np.zeros((3,3))
```
