# Number Theory 

**Number theory** explores what numbers are, how they behave, and why number systems exist the way they do.

---

## Number Systems Overview

### Natural Numbers (ℕ)
- Positive counting numbers: 1, 2, 3, ...
- Oldest known number system.
- Used by early humans for tallying.

### Whole Numbers
- Natural numbers + 0.
- The concept of “0” was introduced for placeholders (e.g., 10, 1000).

### Integers (ℤ)
- Includes negative numbers, 0, and positive numbers.
- Essential for operations like subtraction.
- **Brahmagupta (628 AD)** formalized negative numbers in arithmetic.

### Rational Numbers (ℚ)
- Any number expressible as a fraction (e.g., 2/3, 6.87, 2).
- Useful for measuring partial quantities (e.g., time, distance, volume).

### Irrational Numbers
- **Cannot** be written as fractions (e.g., π, √2, *e*).
- Infinite non-repeating decimals.
- Legend: Pythagorean Hippasus discovered √2 ≠ rational → reportedly drowned for it.

### Real Numbers (ℝ)
- All rational and irrational numbers.
- Used universally in science and data.

### Complex Numbers (ℂ)
- Involves the square root of negatives (e.g., √-1 = *i*).
- Rare in basic data science; used in fields like signal processing, quantum computing.

---

> In data science, we'll mostly use:  
> **Natural numbers, Integers, Rational, and Real numbers.**
___
___
# Variables in Math and Python

If you've written Python code before, you probably know what a **variable** is. In **mathematics**, a variable is just a name used to represent an unknown or changing number.

For example, `x` might stand for any real number. You can use it in calculations without needing to know the exact value.

---

## Example: Variable Input in Python

```python
x = int(input("Please input a number\n"))
product = 3 * x
print(product)
```

This program asks the user for a number, multiplies it by 3, and prints the result.

---

## Common Variable Names

Some variable names are traditionally used for specific purposes:

- `θ` (theta) → often used for **angles**
- `β` (beta) → often used for **parameters** in statistics (like linear regression)

Since Greek letters are hard to use in code, we usually write them as:

```python
theta = 30.0
beta = 1.75
```

---

## Subscripted Variables

In math, you might see variables with subscripts like `x₁`, `x₂`, and `x₃`. In Python, just treat them as separate variable names:

```python
x1 = 3     # or x_1 = 3
x2 = 10    # or x_2 = 10
x3 = 44    # or x_3 = 44
```

Each subscripted variable holds its own value.
____
____
# Functions in Math and Python

A **function** defines a relationship between input and output values.

- The **input variable** is called the **independent variable** (often `x`).
- The **output variable** is called the **dependent variable** (often `y`).

---

## Example: Linear Function

Consider the function:

```
y = 2x + 1
```

This means:  
For any value of `x`, multiply it by 2 and then add 1 to get `y`.

### Table of Values

| x   | 2x + 1 | y   |
|-----|--------|-----|
| 0   | 2×0 + 1 | 1   |
| 1   | 2×1 + 1 | 3   |
| 2   | 2×2 + 1 | 5   |
| 3   | 2×3 + 1 | 7   |

This shows a **predictable** relationship between `x` and `y`.

---

## Function Notation

Instead of writing `y = 2x + 1`, we can write it using function notation:

```
f(x) = 2x + 1
```

This means "`f` is a function of `x`".

---

## Example: Function in Python

Here's how we can declare and use a function in Python:

```python
def f(x):
    return 2 * x + 1

x_values = [0, 1, 2, 3]
for x in x_values:
    y = f(x)
    print(y)
```

---

## Real Numbers and Continuity

Functions don't have to work with just whole numbers.

Example table using decimals:

| x   | 2x + 1 | y   |
|-----|--------|-----|
| 0.0 | 2×0.0 + 1 | 1.0 |
| 0.5 | 2×0.5 + 1 | 2.0 |
| 1.0 | 2×1.0 + 1 | 3.0 |
| 1.5 | 2×1.5 + 1 | 4.0 |
| 2.0 | 2×2.0 + 1 | 5.0 |
| 2.5 | 2×2.5 + 1 | 6.0 |
| 3.0 | 2×3.0 + 1 | 7.0 |

You can use any number — even fractions or very tiny steps — as input.

### ✅ This means the function `y = 2x + 1` is **continuous**:  
For **every possible value of `x`**, there is a corresponding value of `y`.

---

> We'll use functions like these in machine learning, especially for **linear regression**.
## Plotting a Function with SymPy

To plot math functions in Python, we can use many libraries like **Matplotlib** or **Plotly**.  
In this example, we'll use **SymPy**, which is a symbolic math library that can also generate plots.

> ⚠️ SymPy uses Matplotlib for plotting.  
> Make sure Matplotlib is installed, or it will show a text-based plot instead.

---

## ✅ Example: Plotting a Linear Function

```python
from sympy import symbols, plot

# Declare x as a symbolic variable
x = symbols('x')

# Define the function f(x) = 2x + 1
f = 2 * x + 1

# Plot the function
plot(f)
```

This will open a simple graph of the function **y = 2x + 1**.

If we need to see the output then we need to go the ***practice.ipynb*** files'  **4. Plotting a Function**.

---

## 📦 Installation (if needed)

If we haven't already installed SymPy and Matplotlib:

```bash
pip install sympy matplotlib
```
___

> CURVILINEAR FUNCTIONS:
> When a function is continuous but curvy, rather than linear and straight, we call it a
> curvilinear function.

✅ Example:
```python
from sympy import *
x = symbols('x')
f = x**2 + 1
plot(f)
```
For output need to visit **practice.ipynb** files' **5. Plotting a Quadratic Function**.
___
## Functions with Multiple Variables

Functions can take more than one input (independent variable).  
For example:

```
f(x, y) = 2x + 3y
```

Here, both `x` and `y` are independent, and the function returns a **single output** value.  
Since it involves two variables, the output forms a **3D surface** instead of a 2D line.

---

## ✅ Example: 3D Plot with SymPy

```python
from sympy import symbols
from sympy.plotting import plot3d

# Declare two independent variables
x, y = symbols('x y')

# Define the function f(x, y)
f = 2 * x + 3 * y

# Plot the function in 3D
plot3d(f)
```

This creates a 3D plane showing how `f(x, y)` changes with `x` and `y`.

For output need to visit **practice.ipynb** s' **6. Plotting a 3D Function**.

---

## 📌 Notes

- Even if a function has multiple **input variables**, it usually has **one output**.
- If we need **multiple outputs**, define multiple functions.

---