# Python Practice — Level 2 (For / While / If / Match Combined)

Selected exercises with above-average complexity, solved during practice sessions based on Amirhossein Moallemi's Python course (up to Session 4).

---

## 1. Sum of a Nested List (Matrix)

Given a nested list `matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]`, calculate the sum of all its elements using nested `for` loops.

```python
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
total = 0
for row in matrix:
    for num in row:
        total += num
print(total)
```

**Output:** `45`

---

## 2. Character Frequency Counter

Given a string `s = "programming"`, count the frequency of each character using a `for` loop and a dictionary.

```python
s = "programming"
count = {}
for char in s:
    if char in count:
        count[char] += 1
    else:
        count[char] = 1
print(count)
```

**Output:** `{'p': 1, 'r': 2, 'o': 1, 'g': 2, 'a': 1, 'm': 2, 'i': 1, 'n': 1}`

---

## 3. Prime Number Checker

Given `n = 29`, check whether `n` is a prime number using a `while` loop and `if` statements.

```python
n = 29
i = 2
is_prime = True
while i < n:
    if n % i == 0:
        is_prime = False
        break
    i += 1
if n < 2:
    print("not prime")
elif is_prime:
    print("prime")
else:
    print("not prime")
```

**Output:** `prime`

---

## 4. Star Triangle Pattern

Given `n = 5`, print a triangle of stars using nested `for` loops — row 1 has 1 star, row 2 has 2 stars, ... up to row `n`.

```python
n = 5
for i in range(1, n + 1):
    for j in range(i):
        print("*", end=" ")
    print()
```

**Output:**
```
* 
* * 
* * * 
* * * * 
* * * * * 
```

---

## 5. Average Grades from a Dictionary of Lists

Given `grades = {"Ali": [15, 18, 12], "Sara": [20, 19, 18], "Reza": [10, 8, 14]}`, calculate and print the average score of each student in the format `name: average`.

```python
grades = {"Ali": [15, 18, 12], "Sara": [20, 19, 18], "Reza": [10, 8, 14]}
for name, scores in grades.items():
    total = 0
    for score in scores:
        total += score
    average = total / len(scores)
    print(name, ":", average)
```

**Output:**
```
Ali : 15.0
Sara : 19.0
Reza : 10.666666666666666
```

---

## 6. Longest Word in a Sentence (without `max`)

Given `sentence = "the quick brown fox jumps over the lazy dog"`, find the longest word without using the built-in `max` function.

```python
sentence = "the quick brown fox jumps over the lazy dog"
longest_word = ""
for word in sentence.split():
    if len(word) > len(longest_word):
        longest_word = word
print(longest_word)
```

**Output:** `quick`
