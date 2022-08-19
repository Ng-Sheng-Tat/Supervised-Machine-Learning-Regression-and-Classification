## Difference between Copy and Deep Copy

- [link](https://youtu.be/RQ6Ur_T0G3Y)

**Immutable Type**

```
# for immutable type
ori = 5
cpy = ori
cpy = 6

# this is still fine without any inteference
```

**Mutable Type**
```
ori = [0, 1, 2]
cpy = ori
cpy[0] = 5

# this will change the original list value
```

### Shallow Copy: one level deep, only reference of nested child objects
```
import copy
ori = [0, 1, 2]

# alternative 1
cpy = ori.copy()

# alternative 2
cpy = copy.copy(ori)

cpy[0] = 5

# the problem comes when you are exceeding one layer deep inside
ori = [[0, 1, 2], [3,4,5]]

# alternative 1
cpy = ori.copy()

# alternative 2
cpy = copy.copy(ori)

cpy[0][1] = 5

```


### Deep Copy: Full independent copy
```
import copy
ori = [[0, 1, 2], [3,4,5]]

cpy = copy.deepcopy(ori)

cpy[0][1] = 5
```

- this concept is applied to self-defined class and object blueprints
