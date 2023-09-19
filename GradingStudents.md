**Approach JavaScript:**

```javascript
function roundOf(grade) {
  let temp = grade;
  while (temp % 5 != 0) {
    temp += 1;
  }
  const result = temp - grade < 3 ? temp : grade;
  return result;
}

function gradingStudents(grade) {
  let result = [];
  for (const grade of grades) {
    if (grade < 40 && roundOf(grade) < 40) {
      result.push(grade);
    } else {
      result.push(roundOf(grade));
    }
  }
  return result;
}

const grades = [73, 67, 38, 33]; // 75 67 40 33
console.log(gradingStudents(grades));
```

**Approach Python:**

```python
def roundOf(grade):
    temp = grade
    while(grade % 5 != 0):
        grade += 1

    result = grade if grade - temp < 3 else temp
    return result

def gradingStudents(grades):
    result = []

    for grade in grades:
        if grade < 40 and roundOf(grade) < 40:
            result.append(grade)
        else:
            result.append(roundOf(grade))

    return result

grades = [73, 67, 38, 33] # 75 67 40 33
print(gradingStudents(grades))
```
