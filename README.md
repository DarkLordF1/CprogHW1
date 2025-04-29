Here’s a GitHub-friendly **README.md** based on your document:

```markdown
# Homework 1 — C Programming Test Suite

A plug-and-play automated test runner for C programming assignments.  
Simply compile your C solution(s), configure your test cases, and let the Python test runner do the rest.

---

## 📂 Repository Structure

```
.
├── q1.c                      # Your C source for Question 1
├── q2.c                      # Your C source for Question 2
├── q1_test_runner.py         # Python test runner for Question 1
├── q2_test_runner.py         # Python test runner for Question 2
├── test_cases.json           # JSON mapping inputs/outputs for each question
└── hw1_questionX/            # Add question-specific test folders here
    ├── Test1/
    │   ├── input.txt
    │   └── output.txt
    ├── Test2/
    │   ├── input.txt
    │   └── output.txt
    └── …  
```

- **hw1_questionX/**: one folder per question (e.g. `hw1_question1/`, `hw1_question2/`), each containing numbered `TestN` subfolders with `input.txt` and `output.txt`.
- **test_cases.json**: lists the paths to each `TestN` folder for the runner.
- **q?_test_runner.py**: reads `test_cases.json`, feeds each `input.txt` to your compiled program, and checks against `output.txt`.

---

## ⚙️ Prerequisites

- **C compiler**: `gcc` or `clang`
- **Python 3** (for the test runner script)

---

## 🏗️ Setup & Usage

1. **Compile** your C source(s).  
   ```bash
   # Question 1
   clang q1.c -o q1.exe
   # Question 2
   clang q2.c -o q2.exe

   # Or with gcc (no .exe on macOS/Linux):
   gcc q1.c -o q1
   gcc q2.c -o q2
   ```
2. **Organize** your test folders under `hw1_questionX/`.  
   - Each `TestN` folder must contain:
     - `input.txt`  
     - `output.txt`
3. **Configure** `test_cases.json` with the correct relative paths to each `TestN` folder.
4. **Run** the Python test runner:
   ```bash
   python3 q1_test_runner.py   # Runs Question 1 tests
   python3 q2_test_runner.py   # Runs Question 2 tests
   ```
5. **Review** the output:
   - ✅ Passed tests will show a checkmark.
   - ❌ Failed tests will display input, expected vs. actual output.

---

## 📋 Test Case Summaries

### Question 1 — Reverse Digits
- **Behavior**:  
  - Reads an integer (including `0` and negatives).  
  - Prints its digits in reverse order.

| Test | Input    | Expected Output                      |
|:----:|:--------:|:------------------------------------:|
| 1    | `0`      | `Reverse of the number is: 0`        |
| 2    | `7`      | `Reverse of the number is: 7`        |
| 3    | `1000`   | `Reverse of the number is: 1`        |
| 4    | `-123`   | `Reverse of the number is: -321`     |
| 5    | `-1200`  | `Reverse of the number is: -21`      |
| 6    | `214748364`  | `Reverse of the number is: 463847412` |
| 7    | `-1000000000` | `Reverse of the number is: -1`       |

---

### Question 2 — Print Divisors
- **Behavior**:  
  - Reads a non-negative integer.  
  - If `0`, prints:  
    ```
    0 has no Divisors!
    ```
  - Otherwise, lists all positive divisors in ascending order.

| Test | Input       | Expected Output                                      |
|:----:|:-----------:|:-----------------------------------------------------:|
| 1    | `0`         | `0 has no Divisors!`                                 |
| 2    | `1`         | `Divisors of 1 are: 1`                               |
| 3    | `7`         | `Divisors of 7 are: 1 7`                             |
| 4    | `36`        | `Divisors of 36 are: 1 2 3 4 6 9 12 18 36`           |
| 5    | `1000`      | `Divisors of 1000 are: 1 2 4 5 8 10 … 500 1000`      |
| 6    | `7919`      | `Divisors of 7919 are: 1 7919`                       |
| 7    | `2147483647`| `Divisors of 2147483647 are: 1 2147483647`           |

---

## 🔧 Notes

- The runner relies on **file-based I/O**, making it easy to add complex test cases.
- No extra C libraries are required—just `<stdio.h>`.
- The Python scripts are **plug-and-play**; edit only `test_cases.json` if you move test folders.

---

## 👤 Author

**Aiman Abed**  
_Course: C Programming – Homework 1 Test Automation_

Feel free to fork, extend, or adapt this framework for your own C assignments!  
```
