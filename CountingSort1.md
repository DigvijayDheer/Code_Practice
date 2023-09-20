**Approach JavaScript:**

```javascript
function countingSort(arr) {
  let frequency = new Array(100).fill(0);
  for (const num of arr) {
    frequency[num] += 1;
  }
  return frequency;
}

const arr = [1, 1, 3, 2, 1];
console.log(countingSort(arr));
```

**Approach Python:**

```python
def countingSort(arr):
    frequency = [0] * 100
    for num in arr:
        frequency[num] += 1

    return frequency

arr = [1, 1, 3, 2, 1]
print(countingSort(arr))
```
