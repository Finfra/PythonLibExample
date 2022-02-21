# Numpy Matrix
Numpy 로 Matrix를 생성하는 방법들을 알아봅니다.

## Import
보통 np 로 줄여서 많이 쓰입니다.


```python
import numpy as np
```

## 직접 matrix 를 생성하는 방법


```python
x = np.matrix('1 2; 3 4')
print (x)
```

## reshape 를 통해 생성하는 방법


```python
np.arange(25).reshape((5,5))
```


```python
np.array(range(25)).reshape((-1, 5))
```


```python
a=np.ones(12)
a=a.reshape(-1,3)
a
```

## Array 를 Matrix 형태로 생성하기


```python
np.ndarray((5,5))
```

## 값에 접근하는 방법<BR>
- a 라는 matrix 를 생성한다.


```python
a=np.array([[1, 2],[3, 4]])
a
```

- a[행][렬] 의 형식으로 접근한다.


```python
a[1][0]
```

# Matrix Examples
2차원으로 3차원 만들기
- 일괄 생성시 상위 차원 1 추가하기
- 숫자 입력시 각 괄호 입력


```python
i1 = np.ones((1,2,2))
i1
```


```python
i2 = np.array([[[1,2,],[3,4]]])
i2.shape
```


```python
a = np.vstack( (i1, i2, i1))
print (f"{a.shape}\n\n{a}")
```
