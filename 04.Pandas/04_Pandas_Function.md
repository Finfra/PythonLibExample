# Pandas Function

## Import
보통 pd 로 많이 사용합니다.


```python
import pandas as pd
```

## replace

### Regexp


```python
raw_data = {'c1': [1, 2, 3, 4],
            'c2': [10, 20, 30, 40],
            'c3': [100, 200, 300, 400]}

df = pd.DataFrame(raw_data)
print(df)
```


```python
s1 = df['c1'].replace(r'(\d+\.\d*).*',r'\1',regex=True)
s1
```


```python
df1 = df.replace(r'(\d+\.\d*).*',r'\1',regex=True)
df1
```

## 미제 - 데이터의 생성관련

출처. [wikidok](https://wikidocs.net/4367)


```python
dumi = {'c1':  [1, 2, 3, 4, 5],
        'c2':  [10, 20, 30, 40, 50],
        'c3' :  [100, 200, 300, 400, 500],
        'c4': [1000, 2000, 3000, 4000, 5000]}
```


```python

df = pd.DataFrame(dumi, columns=['c4', 'c1', 'c2', 'c3'])
df
```


```python
date = ['21.02.29', '21.03.26', '21.04.25', '21.05.24', '21.06.23']
df_date = pd.DataFrame(dumi, columns=['c4', 'c1', 'c2', 'c3'], index=date)
df_date
```


```python
dir(pd)
```


```python
help(pd.merge)
```


```python
pd.test(df)
```


```python

```
