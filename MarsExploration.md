**Approach JavaScript:**

```javascript
function marsExploration(signal) {
  const expectedSignal = "SOS";
  let changedCount = 0;

  for (let i = 0; i < signal.length; i++) {
    if (signal[i] != expectedSignal[i % 3]) {
      changedCount += 1;
    }
  }

  return changedCount;
}

// Example usage:
const received_signal = "OOSDSSOSOSWEWSOSOSOSOSOSOSSSSOSOSOSS";
const changed_letters = marsExploration(received_signal);
console.log(changed_letters); // Output will be 20
```

**Approach Python:**

```python
def marsExploration(s):
    expected_signal = "SOS"
    changed_count = 0

    for i in range(len(s)):
        if s[i] != expected_signal[i % 3]:
            changed_count += 1

    return changed_count

# Example usage:
received_signal = "SOSSPSSQSSOR"
changed_letters = marsExploration(received_signal)
print(changed_letters)  # Output will be 3

```
