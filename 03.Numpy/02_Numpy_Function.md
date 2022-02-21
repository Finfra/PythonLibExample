# Numpy Fuction Example
Numpy 에서 Data를 다룰 때 쓰이는 Fuction 들을 알아봅니다.

## Import 


```python
import numpy as np
```

## Arange 함수
반열린구간 [start, stop) 에서 step 의 크기만큼 일정하게 떨어져 있는 숫자들을 array 형태로 반환해 주는 함수다.

출처: https://codepractice.tistory.com/88 [코딩 연습]

stop 매개변수의 값만 전달하면 0을 시작으로 1 간격으로 떨어진 수들을 반환한다.


```python
np.arange(5)
```

start 와 stop 이 주어진 경우로 반열린구간 [start, stop) 에서 start 를 시작으로 1 간격으로 떨어진 수들을 반환한다.


```python
np.arange(3,7)
```

start, stop, step 이 모두 주어지면 start 를 시작으로  stop 이 되기 전까지의 step 간격으로 떨어진 수들을 반환한다.


```python
np.arange(3,9,2)
```

## abs 함수
- 절대값을 리턴.


```python
arr=np.array([[1,2,],[3,-4]])
np.abs(arr)
```

## sqrt 함수
- 제곱근(루트)을 계산함.


```python
np.sqrt(arr)
```




    array([[1.        , 1.41421356],
           [1.73205081,        nan]])



## 행렬곱하기
- * 를 통해 곱하기 가능


```python
arr*arr
```

## dot 함수
두 1차원 어레이 a, b의 곱에 대해, np.dot(a, b)는 두 벡터의 내적 (Dot product)을 반환합니다.<br>
(0차원, 2차원은 * 를 권장합니다.)


```python
np.dot(arr[0],arr[1])
```

## Function
|함 수                  |설 명                                                     |비고                          |
|---------------------|--------------------------------------------------------|----------------------------|
|abs, fabs            |절대값을 리턴. 복소수가 아닌 경우에는 빠른 연산을 위해 fabs를  이용한다.            |numpy.abs(arr)              |
|sqrt                 |제곱근(루트)을 계산함.                                           |numpy.sqrt(arr)             |
|square               |제곱을 계산함.                                                |numpy.square(arr)           |
|Exp                  |지수를 계산함.                                                |numpy.Exp(arr)              |
|Log                  |로그를 계산함.                                                |numpy.Log(arr)              |
|sign                 |각 원소의 부호를 계산함. 양수 : 1, 음수 : -1                          |numpy.sign(arr)             |
|ceil                 |소수를 올림으로 계산함.                                           |numpy.ceil(arr)             |
|floor                |소수를 버림으로 계산함.                                           |numpy.floor(arr)            |
|rint                 |소수를 반올림한다. type은 유지된다.                                  |numpy.rint(arr)             |
|modf                 |각 원소의 몫과 나머지를 리턴한다. 두 개의 ndarray를 리턴한다.                 |numpy.modf(arr)             |
|isnan                |숫자인지 아닌지를 판별해서 불리언 배열을 리턴한다.                            |numpy.isnan(arr)            |
|add                  |두 배열을 더한다.                                              |numpy.add(arr1, arr2)       |
|subtract             |첫 번째 배열에서 두 번째 배열을 뺀다.                                  |numpy.subtract(arr1, arr2)|
|multiply             |두 배열을 곱한다.                                              |numpy.multiply(arr1, arr2)|
|divide, floor_divide|첫 번째 배열에서 두 번째 배열을 나눈다. floor_divide는 몫만 리턴한다.          |numpy.divide(arr1, arr2)    |
|power                |첫 번째 배열의 원소를 두 번째 배열의 원소의 값 만큼 제곱한다.                    |numpy.power(arr1, arr2)     |
|maxinum, fmax        |두 배열 중 큰 값을 리턴한다. fmax는 NaN을 무시한다.                      |numpy.maximum(arr1, arr2)   |
|minimum, fmin        |두 배열 중 작은 값을 리턴한다. fmin은 NaN을 무시한다.                     |numpy.minimum(arr1, arr2)   |
|mod                  |첫 번째 배열에서 두 번째 배열을 나눈 나머지를 리턴한다.                        |numpy.mod(arr1, arr2)       |
|greater, less, equal|첫 번째 배열 원소와 두 번째 배열 원소간의 >, <, = 조건 결과를 불리언 배열로 리턴한다.|numpy.greater(arr1, arr2)   |



```python

```
