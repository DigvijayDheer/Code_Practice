**Approach JavaScript:**

```javascript
function findMedian(arr) {
  const sortedArr = arr.slice().sort((a, b) => a - b); // Use slice to create a copy and sort numerically.
  const n = sortedArr.length;
  let median = 0;
  if (n % 2 === 1) {
    median = sortedArr[Math.floor(n / 2)]; // Use Math.floor to get the middle element for odd length.
  } else {
    const mid1 = sortedArr[n / 2 - 1];
    const mid2 = sortedArr[n / 2];
    median = (mid1 + mid2) / 2;
  }
  return median;
}

let arr = [0, 1, 2, 4, 6, 5, 3];
console.log(findMedian(arr));
```

**Approach Python:**

```python
arr = [0, 1, 2, 4, 6, 5, 3]

def findMedian(arr):
    sorted_arr = sorted(arr)  # Create a sorted copy of the list
    n = len(sorted_arr)

    if n % 2 == 1:
        # If the length of the array is odd, return the middle element
        median = sorted_arr[n // 2]
    else:
        # If the length of the array is even, return the average of the two middle elements
        median = (sorted_arr[n // 2 - 1] + sorted_arr[n // 2]) / 2

    return median

print(findMedian(arr))
```
