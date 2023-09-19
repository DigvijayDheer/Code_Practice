**Approach JavaScript:**

```javascript
function miniMaxSum(arr) {
  const totalSum = arr.reduce((acc, val) => acc + val, 0);
  const minVal = Math.min(...arr);
  const maxVal = Math.max(...arr);

  const minSum = totalSum - maxVal;
  const maxSum = totalSum - minVal;

  console.log(minSum, maxSum);
}

// Example usage:
const arr = [1, 3, 5, 7, 9];
miniMaxSum(arr);
```

**Approach Python:**

```python
def miniMaxSum(arr):
    total_sum = sum(arr)
    min_val = min(arr)
    max_val = max(arr)

    min_sum = total_sum - max_val
    max_sum = total_sum - min_val

    print(min_sum, max_sum)

# Example usage:
arr = [1, 3, 5, 7, 9]
miniMaxSum(arr)
```
