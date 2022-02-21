```python
from os.path import join,isfile,isdir
import pandas as pd
url = 'http://j.finfra.com/_file/emp.csv'
dPath='/tmp/emp.csv'  
if not isfile(dPath) :
  !pwd
  storage_options = {'User-Agent': 'Mozilla/5.0'}
  df = pd.read_csv(url)
  df.to_csv(dPath,index=False)
else:
  df = pd.read_csv(dPath)
    
```


```python
df
```


```python
import pandas as pd
url = 'http://j.finfra.com/_file/example.tsv'
dPath='/tmp/example.tsv'

if not isfile(dPath) :
  !pwd
  storage_options = {'User-Agent': 'Mozilla/5.0'}
  df = pd.read_table(url)
  df.to_csv(dPath,index=False,sep="\t")
else:
  df = pd.read_csv(dPath,sep="\t")
```


```python
!rm {dPath}
```


```python
df
```


```python

```
