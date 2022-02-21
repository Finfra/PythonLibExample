# Pandas에는 여러 라이브러리가 있음. 


```python
import numpy as np
# import inspect;_n="np";print('\n'.join([_m for _m in dir(eval(_n)) if inspect.ismodule(eval("%s.%s"%(_n,_m) ))  ] ))
```

* [emath](https://numpy.org/doc/stable/reference/routines.emath.html)
* [ctypeslib](https://numpy.org/doc/stable/reference/routines.ctypeslib.html)
* [fft](https://numpy.org/doc/stable/reference/routines.fft.html)
* [linalg](https://numpy.org/doc/stable/reference/routines.linalg.html)
* [matlib](https://numpy.org/doc/stable/reference/routines.matlib.html)
* [random](https://numpy.org/doc/stable/reference/random/index.html)
* [testing](https://numpy.org/doc/stable/reference/routines.testing.html)


# 이하 복붙해서 사용


```python
libs = ["char","compat","core","ctypeslib","emath","fft","lib","linalg","ma","math","matrixlib","os","polynomial","random","rec","sys","testing","version","warnings"]
for l in libs:
    print('help(np.%s)'%l)
```


```python
help(np.linalg)
```

# LinAlg

## inv 

* y=2x+1 , y=-x+4
* 열행렬 계산을 통한 방정식 풀이가 가능


```python
import numpy as np
a=np.array([[1, -2], [1, 1]])
b=np.array([[1], [4]])
np.dot(np.linalg.inv(a),b)
```

* y:3
* x:1




```python

```
