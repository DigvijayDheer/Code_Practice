**Approach 1 JavaScript:**

```javascript
function divisibleSumPairs(n, k, arr) {
  let count = 0;
  for (let i = 0; i < n; i++) {
    for (let j = i + 1; j < n; j++) {
      let temp = arr[i] + arr[j];
      if (temp % k == 0) {
        count += 1;
      }
    }
  }
  return count;
}

let n = 6;
let k = 3;
let arr = [1, 3, 2, 6, 1, 2]; // output: 5
console.log(divisibleSumPairs(n, k, arr));
```

**Approach 2 JavaScript:**

```javascript
function divisibleSumPairs(n, k, arr) {
  let count = 0;
  let remainderCount = new Array(k).fill(0);

  for (let num of arr) {
    let remainder = num % k;
    count += remainderCount[(k - remainder) % k];
    remainderCount[remainder] += 1;
  }

  return count;
}

let n = 6;
let k = 3;
let arr = [1, 3, 2, 6, 1, 2]; // output: 5
console.log(divisibleSumPairs(n, k, arr));
```

**Approach 1 Python:**

```python
def divisibleSumPairs(n, k, ar):
    count = 0
    for i in range(0, n):
        for j in range(i + 1, n):
            temp = ar[i] + ar[j]
            if temp % k == 0:
                count += 1
    return count

n = 6
k = 3
ar = [1, 3, 2, 6, 1, 2] # output: 5
print(divisibleSumPairs(n, k, ar))
```

**Approach 2 Python:**

```python
def divisibleSumPairs(n, k, ar):
    count = 0
    remainder_count = [0] * k  # Initialize an array to store counts of remainders

    for num in ar:
        remainder = num % k
        count += remainder_count[(k - remainder) % k]
        remainder_count[remainder] += 1

    return count

n = 6
k = 3
ar = [1, 3, 2, 6, 1, 2]  # output: 5
print(divisibleSumPairs(n, k, ar))
```
