**Approach 1 JavaScript:**

```javascript
const stringArray = [
  "S;M;plasticCup()", // plastic cup
  "S;C;LargeSoftwareBook", // large software book
  "S;V;pictureFrame", // picture frame
  "C;M;white sheet of paper", // whiteSheetOfPaper()
  "C;C;coffee machine", // CoffeeMachine
  "C;V;mobile phone", // mobilePhone
];

function splitString(string) {
  let word = "";
  let currentWord = "";
  for (const char of string) {
    if (char === char.toUpperCase() && currentWord) {
      word += currentWord + " ";
      currentWord = char;
    } else {
      currentWord += char;
    }
  }
  if (currentWord) {
    word += currentWord;
  }
  return word.toLowerCase();
}

function combinedString(string) {
  const words = string.split(" ");
  let result = "";
  for (let i = 0; i < words.length; i++) {
    if (i === 0) {
      result += words[i];
    } else {
      result += words[i][0].toUpperCase() + words[i].slice(1);
    }
  }
  return result;
}

function splitMethod(string) {
  if (string.slice(-2) === "()") {
    string = string.slice(0, -2);
  }
  return splitString(string);
}

function splitVariable(string) {
  return splitString(string);
}

function splitClass(string) {
  return splitString(string);
}

function createVariable(string) {
  return combinedString(string);
}

function createMethod(string) {
  return combinedString(string) + "()";
}

function createClass(string) {
  const words = string.split(" ");
  let result = "";
  for (let i = 0; i < words.length; i++) {
    result += words[i][0].toUpperCase() + words[i].slice(1);
  }
  return result;
}

function camelCase(string) {
  const strArr = string.split(";");
  if (strArr[0] === "C") {
    if (strArr[1] === "M") {
      return createMethod(strArr[2]);
    }
    if (strArr[1] === "V") {
      return createVariable(strArr[2]);
    }
    if (strArr[1] === "C") {
      return createClass(strArr[2]);
    }
  }
  if (strArr[0] === "S") {
    if (strArr[1] === "M") {
      return splitMethod(strArr[2]);
    }
    if (strArr[1] === "V") {
      return splitVariable(strArr[2]);
    }
    if (strArr[1] === "C") {
      return splitClass(strArr[2]);
    }
  }
}

stringArray.forEach((string) => {
  console.log(camelCase(string));
});
```

**Approach 2 JavaScript:**

```javascript
const stringArray = [
  "S;M;plasticCup()", // plastic cup
  "S;C;LargeSoftwareBook", // large software book
  "S;V;pictureFrame", // picture frame
  "C;M;white sheet of paper", // whiteSheetOfPaper()
  "C;C;coffee machine", // CoffeeMachine
  "C;V;mobile phone", // mobilePhone
];

function camelCase(s) {
  const [sc, mcv, op] = s.split(";");
  if (sc === "S") {
    let cap;
    if (mcv === "M") {
      cap = op.slice(0, -2);
    }
    if (mcv === "C" || mcv === "V") {
      cap = op;
    }
    const result = cap.replace(/(\w)([A-Z])/g, "$1 $2").toLowerCase();
    console.log(result);
  }
  if (sc === "C") {
    const cap = op.replace(/ /g, "").toLowerCase();
    const q = cap.charAt(0).toUpperCase() + cap.slice(1);
    if (mcv === "M") {
      console.log(q + "()");
    }
    if (mcv === "C") {
      console.log(q);
    }
    if (mcv === "V") {
      console.log(q.charAt(0).toLowerCase() + q.slice(1));
    }
  }
}

stringArray.forEach((string) => {
  camelCase(string);
});
```

**Approach 1 Python:**

```python
string_array = [
"S;M;plasticCup()", # plastic cup
"S;C;LargeSoftwareBook", # large software book
"S;V;pictureFrame", # picture frame
"C;M;white sheet of paper",  # whiteSheetOfPaper()
"C;C;coffee machine",  # CoffeeMachine
"C;V;mobile phone",  # mobilePhone
]

# Enter your code here. Read input from STDIN. Print output to STDOUT
def split_string(string):
    word = ""
    current_word = ""
    for char in string:
        if char.isupper() and current_word:
            word += current_word + " "
            current_word = char
        else:
            current_word += char
    if current_word:
        word += current_word
    return word.lower()


def combined_string(string):
    words = string.split(" ")
    result = ""
    for i in range(0, len(words)):
        if i == 0:
            result += words[i]
        else:
            result += words[i].capitalize()
    return result

def split_method(string):
    if string[-2:] == "()":
        string = string[:-2]
    return split_string(string)

def split_variable(string):
    return split_string(string)

def split_class(string):
    return split_string(string)

def create_variable(string):
    return combined_string(string)

def create_method(string):
    return combined_string(string) + "()"


def create_class(string):
    words = string.split(" ")
    result = ""
    for i in range(0, len(words)):
        result += words[i].capitalize()
    return result

def camel_case(string):
    str_arr = string.split(";")

    if str_arr[0] == "C":
        if str_arr[1] == "M":
            return create_method(str_arr[2])

        if str_arr[1] == "V":
            return create_variable(str_arr[2])

        if str_arr[1] == "C":
            return create_class(str_arr[2])

    if str_arr[0] == "S":
        if str_arr[1] == "M":
            return split_method(str_arr[2])

        if str_arr[1] == "V":
            return split_variable(str_arr[2])

        if str_arr[1] == "C":
            return split_class(str_arr[2])

while True:
    try:
        string = input().rstrip()
        print(camel_case(string))

    except EOFError:
        break

# Run the Code:
for string in string_arr:
    print(camel_case(string))
```

**Approach 2 Python:**

```python
import re

string_array = [
"S;M;plasticCup()", # plastic cup
"S;C;LargeSoftwareBook", # large software book
"S;V;pictureFrame", # picture frame
"C;M;white sheet of paper",  # whiteSheetOfPaper()
"C;C;coffee machine",  # CoffeeMachine
"C;V;mobile phone",  # mobilePhone
]

def camel_case(s):
    sc, mcv, op = s.split(";")
    if sc == "S":
        if mcv == "M":
            cap = op[:-2]

        if mcv == "C" or mcv == "V":
            cap = op

        s = re.sub("(\w)([A-Z])", r"\1 \2", cap)
        print(s.lower())

    if sc == "C":
        cap = op.title()
        s = re.sub(r" ", r"", cap)
        q = s[:1].lower() + s[1:]

        if mcv == "M":
            print(q+"()")

        if mcv == "C":
            print(s)

        if mcv == "V":
            print(q)

for string in string_array:
    camel_case(string)
```
