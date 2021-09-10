## pandas
### Info
* Cheat Sheet : https://pandas.pydata.org/Pandas_Cheat_Sheet.pdf
### Setting
* Jupyter에서 줄 제한 늘리기
```
pd.set_option('display.max_rows', 80)
```
### Basic
```
df=pd.DataFrame( np.array( range(24)).reshape((8,3)))
df[df.columns[1] ]       # col
df[[1]]
df.loc[ [1,2] ]         # row
```
### Pandas데이터 가공 Example
```
import pandas as pd
#dir(pd)
#help(pd.read_csv)
emp=pd.read_csv("/Users/Shared/__BigData/__data/emp.csv")
emp

#select ename,sal from emp
emp.ix[:,(1,5)]

#select * from emp where deptno =10
emp[emp.deptno==10]

#select * from emp  oder by sal
emp.sort_values(by=["sal"])

#select ename,sal from emp where deptno =10 oder by sal
e=emp.ix[:,(1,5)]
e[emp.deptno==10].sort_values(by=["sal"])

# DropColumn
e.drop(['sal'],axis=1,inplace=True)

```

### Select Example
* Column별
```
emp=pd.read_csv("/Users/Shared/__BigData/__data/emp.csv")
for col in emp:
    print(col,emp[col])
```
* Row별
```
for i,r in emp.iterrows():
    print(i,'----------------------')
    for j in r:
        print(j)

```


* cf) Comparison with SQL : https://pandas.pydata.org/pandas-docs/stable/comparison_with_sql.html

### Correlation
```
lst = [[1,2,3,4,5,6,7],
        [10,15,20,25,50,55,60],
        [0,0,0,0,0,0,0],
        [-1,-20,-30,-45,-50,-55,-70]]

df = pd.DataFrame(lst).T
corr = df.corr(method = 'pearson')
print(corr)

print(corr.index[abs(corr["PRICE"])>=0.45])

```




### Normalization
* Basic
```
def norm(x):
    _max = x.max()
    _min = x.min()
    _denom = _max - _min
    return (x - _min) / _denom
```

* by Pandas
```
from sklearn.preprocessing import MinMaxScaler
min_max_scaler = MinMaxScaler()
fitted = min_max_scaler.fit(df)
print(fitted.data_max_ , fitted.data_min_)

output = min_max_scaler.transform(df)
print(output)
```

## DataFrame

## Series
* astype
```
pd.Series([1, 2], dtype='int32')

df.info()
df.astype('int32').dtypes
df.astype({'col1': 'int32'}).dtypes
```
## Function(DataFrame or Series)
### Replace
* Regexp
```
s1=df['ZN'].replace(r'(\d+\.\d*).*',r'\1',regex=True)

df1=df.replace(r'(\d+\.\d*).*',r'\1',regex=True)

```
