# 1. 아래와 같은 DataFrame 을 만드시오.

| d | su | val |
|:-----:|:-----:|:-----:|
| 2 | 1 | 2 |
| 2 | 2 | 4 |
| . | . | . |
| 9 | 9 | 81 |

(o) 'row 를 concat 하는 방식'<BR>
(x) Series 를 만들어 col 추가<BR>
(x) CSV 로드


```python
import pandas as pd
```


```python
pdata = pd.DataFrame(columns = ["d","su","val"])
pdata
```


```python
for i in range(2,10):
  for i2 in range(1,10):
    print(i, i2, i*i2)
```


```python
for i in range(2,10):
  for i2 in range(1,10):
    data = pd.DataFrame([[i,i2,i*i2]],columns = ["d","su","val"])
    pdata = pd.concat([pdata,  data],axis=0, join='inner')
pdata
```

# 2. a 가 NaN 일때 b 를 0 으로 바꾸기

|   | a | b |
|:-----:|:-----:|:-----:|
|  | 11 | 22 |
|  | NaN | 44 |

- tips. np.isnan() 함수를 활용하세요.
- tips2. (np.nan == 데이터) 는 동작하지 않습니다.
- tips3. rp[1], a
- tips4. df.iterrow() 를 활용하면 더 쉽습니다.

## 기본방법


```python
import pandas as pd
import numpy as np
```


```python
pdata = pd.DataFrame([[11., 22.],[np.nan, 44.]], columns = ["a","b"])
pdata
```


```python
for i in pdata.iterrows():
  if ( np.isnan(i[1]["a"])):
    i[1]["b"] = 0
```


```python
pdata
```

## 한줄로 처리하기


```python
pdata2 = pd.DataFrame([[11., 22.],[np.nan, 44.]], columns = ["a","b"])
pdata2
```


```python
pdata2["b"]=[  r[1].b if not np.isnan(r[1].a) else 0 for r in pdata2.iterrows()]
pdata2
```


```python

```
