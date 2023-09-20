**Approach JavaScript:**

```javascript
function isPangram(sentence) {
  // Convert the sentence to lowercase to ensure case-insensitivity
  sentence = sentence.toLowerCase();

  // Create an array of lowercase alphabet letters
  const alphabet = Array.from("abcdefghijklmnopqrstuvwxyz");

  // Iterate through the alphabet and check if each letter is present in the sentence
  for (const letter of alphabet) {
    if (!sentence.includes(letter)) {
      return false; // If any letter is missing, it's not a pangram
    }
  }

  return true; // All letters are present, it's a pangram
}

// Test the function
const sentence1 = "The quick brown fox jumps over the lazy dog.";
const sentence2 = "Hello, world!";

console.log(isPangram(sentence1)); // Output: true
console.log(isPangram(sentence2)); // Output: false
```

**Approach Python:**

```python
def is_pangram(sentence):
    # Convert the sentence to lowercase to ensure case-insensitivity
    sentence = sentence.lower()

    # Create a set of lowercase alphabet letters manually
    alphabet = set(chr(ord('a') + i) for i in range(26))

    # Check if the set of alphabet letters is a subset of the letters in the sentence
    return alphabet.issubset(set(sentence))

# Test the function
sentence1 = "The quick brown fox jumps over the lazy dog."
sentence2 = "Hello, world!"

print(is_pangram(sentence1))  # Output: True
print(is_pangram(sentence2))  # Output: False

```
