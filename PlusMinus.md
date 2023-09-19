**Approach JavaScript:**

```javascript
function plusMinus(arr) {
  const length = arr.length;
  let zeros = 0;
  let positives = 0;
  let negatives = 0;

  for (const number of arr) {
    if (number === 0) {
      zeros++;
    } else if (number > 0) {
      positives++;
    } else {
      negatives++;
    }
  }

  let res = "";
  if (length === 0) {
    // Handle the case where the array is empty
    res = "0.000000\n0.000000\n0.000000";
  } else {
    // Calculate fractions and round to 6 decimal places
    res = `${(positives / length).toFixed(6)}\n${(negatives / length).toFixed(
      6
    )}\n${(zeros / length).toFixed(6)}`;
  }

  console.log(res);
}

// Example usage:
const arr = [1, 1, 0, -1, -1];
plusMinus(arr);
```

**Approach Python:**

```python
def plusMinus(arr):
    length = len(arr)
    zeros = 0
    positives = 0
    negatives = 0

    for number in arr:
        if number == 0:
            zeros += 1
        elif number > 0:
            positives += 1
        else:
            negatives += 1

    if length == 0:
        # Handle the case where the array is empty
        res = "0.000000\n0.000000\n0.000000"
    else:
        # Calculate fractions and round to 6 decimal places
        res = f'{positives / length:.6f}\n{negatives / length:.6f}\n{zeros / length:.6f}'

    print(res)

# Example usage:
arr = [1, 1, 0, -1, -1]
plusMinus(arr)
```
