# Yaml Test

## Install


```python
!pip install pyyaml
```

## Load Yaml


```python
import yaml
import json
with open('a.yaml') as f:
    config=yaml.load(f,Loader=yaml.FullLoader)
    print(config)
    
```

## Print as Yaml


```python
print(yaml.dump(config))

```

## Print Beautify Json Style


```python
print(json.dumps(config,indent=2))
```
