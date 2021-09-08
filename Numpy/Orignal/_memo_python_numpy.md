## numpy

### Install
```python
    yum groupinstall 'Development Tools'
    <!-- yum install gcc-gfortran-4.1.2-52.el5_8.1 gcc44-gfortran-4.4.6-3.el5.1 libgfortran.x86_64 lapack.x86_64 blas.x86_64 -->
    yum install blas-devel lapack-devel
    yum install python-devel
    pip install "ipython[notebook]"
    //yum install numpyca
    pip install numpy
```
### Basic Usage
```python
import numpy as np
data = [[1,2],[3,4]]
arr=np.array(data)
arr.shape
arr.ndim
np.empty((3,3))
np.ones((3,3))
np.zeros((3,3))
np.arange(5)
## array([0, 1, 2, 3, 4])
```
### Library
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
### Matrix Basic
```python
import numpy as np
x=np.matrix('1 2; 3 4')
np.arange(25).reshape((5, 5))
np.array(range(25)).reshape((-1, 5))
np.ndarray((5, 5))
a=np.array([[1, 2],[3, 4]])
a[1][1]

a=np.ones(12)
a.reshape(-1,3)

```
### Matrix Examples

* 2차원으로 3차원 만들기
  - 일괄 생성시 상위 차원 1 추가하기
  - 숫자 입력시 각 괄호 입력
```
i1=np.ones((1,2,2))
i2=np.array([[[1,2],[3,4]] ] )

a=np.vstack( (i1,i2,i1) )
print(f"{a.shape}\n\n{a} ")

```

* etc
```python
>>> np.abs(arr)
array([[1, 2],
       [3, 4]])
>>> np.sqrt(arr)
array([[ 1.        ,  1.41421356],
       [ 1.73205081,  2.        ]])
>>> a*a
array([[ 0.,  0.,  0.,  0.],
       [ 0.,  0.,  0.,  0.],
       [ 0.,  0.,  0.,  0.]])
>>> arr*arr
array([[ 1,  4],
       [ 9, 16]])
>>> np.dot([1,0],[[1,0,1],[1,1,np.sqrt(3)]]) # == [  [1,0] · [1,1] ,  [1,0] · [0,1] , [1,0] · [1,np.sqrt(3)]
array([ 1.,  0.,  1.])
>>> np.cross([0.,1.],[1.,0.])
array(-1.0)
>>> a1=np.array([1,2,3]).reshape( [1,3])
>>> a2=np.array([4,5,6]).reshape( [1,3])
>>> np.concatenate((a1,a2),axis=0)
array([[1, 2, 3],
       [4, 5, 6]])

```

### inv example
* y=2x+1 , y=-x+4
```
import numpy as np
a=np.array([[1, -2], [1, 1]])
b=np.array([[1], [4]])
np.dot(np.linalg.inv(a),b)
```
