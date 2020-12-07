---
published: true
---
## Merging Dictionaries

Three ways to merge dictionaries in Python

### Method 1 (none pythonic)

```
dict1 = {'id':1, 'name':'nobody'}
dict2 = {'age':55}
dict3 = {}
for k,v in dict1:
	dict3[k] = dict1[k]
 
for k,v in dict2:
	dict3[k] = dict2[k]
```


### Method 2(comperhension)
```
dict3 = {k:v for d in [dict1,dict2] for k,v in d}
```

### Method 3
```
dict3 = dict1.copy()
dict3.update(dict2)
```

### Method 4(unpackng, only works in 3.5+)
```
dict3 = {**dict1, **dict2}
```
