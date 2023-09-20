**Approach JavaScript:**

```javascript
function countingValleys(steps, path) {
  let altitude = 0; // Initialize altitude to sea level
  let valleyCount = 0; // Initialize the count of valleys

  for (let i = 0; i < steps; i++) {
    const step = path.charAt(i);

    if (step === "U") {
      altitude++; // Going uphill, increase altitude
    } else {
      altitude--; // Going downhill, decrease altitude
    }

    // Check if the hiker entered a valley (altitude went from 0 to -1)
    if (altitude === -1 && step === "D") {
      valleyCount++;
    }
  }

  return valleyCount;
}

// Input from user
// const steps = parseInt(prompt("Enter the number of steps:"));
// const path = prompt("Enter the path:").trim();
// const result = countingValleys(steps, path);
// console.log(`Number of valleys: ${result}`);

const steps1 = 8;
const path1 = "UDDDUDUU";

const steps2 = 12;
const path2 = "DDUUDDUDUUUD";

console.log(countingValleys(steps1, path1)); // 1
console.log(countingValleys(steps2, path2)); // 2
```

**Approach Python:**

```python
def countingValleys(steps, path):
    altitude = 0  # Initialize altitude to sea level
    valley_count = 0  # Initialize the count of valleys

    for step in path:
        if step == 'U':
            altitude += 1  # Going uphill, increase altitude
        else:
            altitude -= 1  # Going downhill, decrease altitude

        # Check if the hiker entered a valley (altitude went from 0 to -1)
        if altitude == -1 and step == 'D':
            valley_count += 1

    return valley_count

# Input
# steps = int(input())
# path = input().strip()

# Calculate and print the number of valleys
# result = countingValleys(steps, path)
# print(result)

steps1 = 8
path1 = "UDDDUDUU"

steps2 = 12
path2 = "DDUUDDUDUUUD"

print(countingValleys(steps1, path1)) # 1
print(countingValleys(steps2, path2)) # 2
```
