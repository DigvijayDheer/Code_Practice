**Approach 1 JavaScript:**

```javascript
function matchingStrings(strings, queries) {
  const results = [];
  for (let q = 0; q < queries.length; q++) {
    results[q] = 0;
    for (let s = 0; s < strings.length; s++) {
      if (strings[s] == queries[q]) {
        results[q] += 1;
      }
    }
  }
  return results;
}

const strings = ["ab", "ab", "abc"];
const queries = ["ab", "abc", "bc"];
const results = matchingStrings(strings, queries);
console.log(results);
```

**Approach 2 JavaScript:**

```javascript
function matchingStrings(strings, queries) {
  const stringCounts = {};
  for (const string of strings) {
    if (string in stringCounts) {
      stringCounts[string] += 1;
    } else {
      stringCounts[string] = 1;
    }
  }

  const results = [];
  for (const query of queries) {
    if (query in stringCounts) {
      results.push(stringCounts[query]);
    } else {
      results.push(0);
    }
  }

  return results;
}

const strings = ["ab", "ab", "abc"];
const queries = ["ab", "abc", "bc"];
const results = matchingStrings(strings, queries);
console.log(results);
```

**Approach 1 Python:**

```python
def matchingStrings(strings, queries):
    result = [0] * len(queries)

    for q in range(len(queries)):
        for s in range(len(strings)):
            if strings[s] == queries[q]:
                result[q] += 1

    return result

strings = ['ab', 'ab', 'abc']
queries = ['ab', 'abc', 'bc']
results = matchingStrings(strings, queries)
print(results)
```

**Approach 2 Python:**

```python
def matchingStrings(strings, queries):
    # Create a dictionary to store the counts of each string in 'strings'
    string_counts = {}
    for s in strings:
        if s in string_counts:
            string_counts[s] += 1
        else:
            string_counts[s] = 1

    # Initialize the result list
    result = []

    # Look up the counts for each query string
    for q in queries:
        if q in string_counts:
            result.append(string_counts[q])
        else:
            result.append(0)

    return result

strings = ['ab', 'ab', 'abc']
queries = ['ab', 'abc', 'bc']
results = matchingStrings(strings, queries)
print(results)
```
