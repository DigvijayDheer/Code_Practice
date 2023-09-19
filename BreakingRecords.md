**Approach JavaScript:**

```javascript
function breakingRecords(scores) {
  if (!scores.length) {
    return [0, 0];
  }

  let maxScore = scores[0];
  let minScore = scores[0];
  let maxCount = 0;
  let minCount = 0;

  for (let i = 1; i < scores.length; i++) {
    const score = scores[i];

    if (score > maxScore) {
      maxScore = score;
      maxCount++;
    } else if (score < minScore) {
      minScore = score;
      minCount++;
    }
  }

  return [maxCount, minCount];
}

// Example usage:
const scores = [12, 24, 10, 24];
const result = breakingRecords(scores);
console.log(result); // Output: [1, 1]
```

**Approach Python:**

```python
def breakingRecords(scores):
    if not scores:
        return [0, 0]

    max_score = scores[0]
    min_score = scores[0]
    max_count = 0
    min_count = 0

    for score in scores[1:]:
        if score > max_score:
            max_score = score
            max_count += 1
        elif score < min_score:
            min_score = score
            min_count += 1

    return [max_count, min_count]

# Example usage:
scores = [12, 24, 10, 24]
result = breakingRecords(scores)
print(result)  # Output: [1, 1]
```
