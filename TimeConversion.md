**Approach JavaScript:**

```javascript
function timeConversion(s) {
  const timeParts = s.split(":");
  let hours = parseInt(timeParts[0]);
  const minutes = parseInt(timeParts[1].slice(0, 2));
  const seconds = parseInt(timeParts[2].slice(0, 2));
  const amPm = timeParts[2].slice(-2);

  if (amPm === "PM" && hours !== 12) {
    hours += 12;
  }

  if (amPm === "AM" && hours === 12) {
    hours = 0;
  }

  const result = `${String(hours).padStart(2, "0")}:${String(minutes).padStart(
    2,
    "0"
  )}:${String(seconds).padStart(2, "0")}`;

  return result;
}

const s = "12:33:45AM";
console.log(timeConversion(s));
```

**Approach Python:**

```python
def convert_to_24_hour(time_12_hour):
    # Split the time string into hours, minutes, and AM/PM
    time_parts = time_12_hour.split(':')
    hours = int(time_parts[0])
    minutes = int(time_parts[1][:2])  # Extract the first 2 characters for minutes
    am_pm = time_parts[1][-2:]  # Extract the last 2 characters for AM/PM

    # Convert to 24-hour format
    if am_pm.lower() == 'pm' and hours != 12:
        hours += 12
    elif am_pm.lower() == 'am' and hours == 12:
        hours = 0

    # Format the result as a 24-hour time string
    result = f"{hours:02d}:{minutes:02d}"
    return result

# Example usage:
time_12_hour = "02:30 PM"
time_24_hour = convert_to_24_hour(time_12_hour)
print(time_24_hour)  # Output: "14:30"
```
