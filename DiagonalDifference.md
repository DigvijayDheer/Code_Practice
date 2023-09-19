**Approach JavaScript:**

```javascript
function diagonalDifference(matrix) {
  const len = matrix.length;
  let mainDiagonalSum = 0;
  let antiDiagonalSum = 0;

  for (const i in matrix) {
    mainDiagonalSum += matrix[i][i];
    antiDiagonalSum += matrix[i][len - 1 - i];
  }

  return Math.abs(mainDiagonalSum - antiDiagonalSum);
}

const matrix = [
  [1, 2, 3],
  [4, 5, 6],
  [9, 8, 9],
];

console.log(diagonalDifference(matrix));
```

**Approach Python:**

```python
def diagonalDifference(matrix):
    # Write your code here
    main_diagonal_sum = 0
    anti_diagonal_sum = 0
    n = len(matrix)
    for i in range(n):
        main_diagonal_sum += matrix[i][i]
        anti_diagonal_sum += matrix[i][n - 1 - i]

    return abs(main_diagonal_sum - anti_diagonal_sum)

matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [9, 8, 9]
]

print(diagonalDifference(matrix)) # 2
```
