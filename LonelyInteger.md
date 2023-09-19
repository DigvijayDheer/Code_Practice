**Approach JavaScript:**

```javascript
function lonelyInteger(arr) {
  let count = {};

  for (const i of arr) {
    if (i in count) {
      count[i] += 1;
    } else {
      count[i] = 1;
    }
  }

  let result = 0;

  for (const i in count) {
    if (count[i] < 2) {
      result = i;
    }
  }

  return result;
}

const arr = [1, 2, 3, 4, 3, 2, 1];
console.log(lonelyInteger(arr));
```

**Approach Python:**

```python
def lonelyinteger(a):
    integer_count = {}

    for i in a:
        if i in integer_count:
            integer_count[i] += 1
        else:
            integer_count[i] = 1

    result = 0

    for i in integer_count:
        if integer_count[i] < 2:
            result = i

    return result

a = [1, 2, 3, 4, 3, 2, 1]
print(lonelyinteger(a))
```
