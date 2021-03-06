# Comparing tensors #
So we've covered the basic math operations between two tensors. We could also use some comparison features and thankfully the're also defined in the [cntk.ops module](https://cntk.ai/pythondocs/_modules/cntk/ops.html):
- less
- equal
- greater
- greater_equal
- not_equal
- less_equal


## Syntaxis ##
These operations share the same arguments pattern:
```console
operationName(arg1, arg2, functionName)
```
- arg1: The first tensor
- arg2: The second tensor
- functionName: Optional, a name for the current operation

Note that they are element by element comparison of two tensors elements.

## Operations ##
Let's define two tensors:

```python
A = [1,3,4]
B = [4,3,2]
```
#### less ####
Result is 
- 1 if left < right, 
- 0 if right <= left
```python
cntk.less(A, B).eval()

output:
[ 1.  0.  0.]
```

#### equal ####
Result is 
- 1 if values are the same
- 0 if values are not the same
```python
cntk.equal(A, B).eval()

output:
[ 0.  1.  0.]
```

#### greater ####
Result is 
- 1 if left > right, 
- 0 if right >= left
```python
cntk.greater(A,B).eval()

output
[ 0.  0.  1.]
```
#### less_equal ####
- 1 if left <= right, 
- 0 if right < left
```python
cntk.less_equal(A,B).eval()

output 
[ 1.  1.  0.]
```

#### not_equal ####
Result is 
- 1 if values are not the same
- 0 if values are the same
```python
cntk.not_equal(A,B).eval()

output
[ 1.  0.  1.]
```
#### greater_equal ####
Result is 
- 1 if left >= right, 
- 0 if right > left
```python
cntk.greater_equal(A,B).eval()

output
[ 0.  1.  1.]
```