# Python Practice — Level 3 (For / While / If / Match Combined — Advanced)

Selected exercises with above-average complexity, solved during practice sessions based on Amirhossein Moallemi's Python course (up to Session 4).

---

## 1. Filtering a List of Dictionaries

Given a list of dictionaries `data`, print the name of every student whose score is above 80.

```python
data = [
    {"name": "Ali", "score": 85},
    {"name": "Sara", "score": 92},
    {"name": "Reza", "score": 78},
]
for student in data:
    if student["score"] > 80:
        print(student["name"])
```

**Output:**
```
Ali
Sara
```

---

## 2. Sum of Squares with a Condition (while loop)

Given `n = 17`, calculate the sum of squares of numbers from 1 to `n` that are divisible by 3, using a `while` loop.

```python
n = 17
total = 0
i = 1
while i <= n:
    if i % 3 == 0:
        total += i**2
    i += 1
print(total)
```

**Output:** `495`

---

## 3. Flattening a Nested List (Matrix)

Given a nested list `matrix`, flatten it into a single-level list using nested `for` loops.

```python
matrix = [[1, 2], [3, 4], [5, 6]]
flat_list = []
for row in matrix:
    for element in row:
        flat_list.append(element)
print(flat_list)
```

**Output:** `[1, 2, 3, 4, 5, 6]`

---

## 4. Categorizing Words by Length (using `match` with guard clauses)

Given a set of words, categorize each one as `"short"` (< 5 chars), `"medium"` (5–7 chars), or `"long"` (> 7 chars) using `match` with guard conditions.

```python
words = {"apple", "banana", "cherry", "date", "elderberry"}
for word in words:
    length = len(word)

    match length:
        case l if l < 5:
            category = "short"
        case l if 5 <= l <= 7:
            category = "medium"
        case _:
            category = "long"
    print(f"{word} : {category}")
```

**Output (set order may vary):**
```
apple : short
banana : medium
cherry : medium
date : short
elderberry : long
```

---

## 5. Filtering Tuple Records with Unpacking

Given a list of tuple records `(name, age, city)`, print only the records where age is greater than 23.

```python
records = [("Ali", 25, "Tehran"), ("Sara", 30, "Isfahan"), ("Reza", 22, "Shiraz")]
for name, age, city in records:
    if age > 23:
        print(f"{name} is from {city}")
```

**Output:**
```
Ali is from Tehran
Sara is from Isfahan
```

---

## 6. Generating the Fibonacci Sequence

Given `n = 30`, generate and print the Fibonacci sequence (starting from 0, 1) up to and including numbers less than or equal to `n`.

```python
n = 30
a = 0
b = 1
print(a)
while b <= n:
    print(b)
    a, b = b, a + b
```

**Output:**
```
0
1
1
2
3
5
8
13
21
```

---

## 7. Word Frequency Counter Across Multiple Sentences

Given a list of sentences, count the frequency of each word across all sentences combined, using nested loops.

```python
sentences = ["I love python", "python is fun", "I love coding"]
word_count = {}
for sentence in sentences:
    words = sentence.split()
    for word in words:
        if word in word_count:
            word_count[word] += 1
        else:
            word_count[word] = 1
print(word_count)
```

**Output:** `{'I': 2, 'love': 2, 'python': 2, 'is': 1, 'fun': 1, 'coding': 1}`

---

## 8. Multi-Condition Classification with `match`

Given a list of numbers, classify each one using `match` on a tuple of boolean conditions: `"both"` if divisible by 2 and 3, `"even"` if only by 2, `"three"` if only by 3, otherwise print the number itself.

```python
numbers = [15, 8, 23, 4, 42, 16, 9]
for num in numbers:
    match (num % 2 == 0, num % 3 == 0):
        case (True, True):
            print("both")
        case (True, False):
            print("even")
        case (False, True):
            print("three")
        case _:
            print(num)
```

**Output:**
```
three
even
23
even
both
even
three
```

---

## 9. Summing Values from a Nested Dictionary

Given a nested dictionary of orders (each containing quantity and price), calculate the total cost across all orders.

```python
orders = {
    "order1": {"item": "book", "qty": 3, "price": 20},
    "order2": {"item": "pen", "qty": 10, "price": 2},
    "order3": {"item": "laptop", "qty": 1, "price": 1000},
}
total = 0
for order in orders.values():
    total += order["qty"] * order["price"]
print(total)
```

**Output:** `1080`
