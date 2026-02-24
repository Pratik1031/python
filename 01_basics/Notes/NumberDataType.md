# Numbers Data Type in Python (Depth)

Python provides three distinct numeric types: **Integers**, **Floating point numbers**, and **Complex numbers**. Additionally, **Booleans** are a subtype of integers.

---

## 1. Integers (`int`)

Python's `int` type represents whole numbers. Unlike many other languages, Python integers have **arbitrary precision**, meaning they can be as large as your computer's memory allows.

### Key Characteristics:
- **No Overflow**: You don't have to worry about 32-bit or 64-bit limits. Python handles large numbers automatically.
- **Internal Representation**: Python uses a variable-length array of "digits" (usually 30-bit chunks) to represent large integers.

### Number Bases:
You can represent integers in different bases using prefixes:
- **Decimal**: Default (e.g., `100`)
- **Binary**: `0b` or `0B` (e.g., `0b1101` is 13)
- **Octal**: `0o` or `0O` (e.g., `0o17` is 15)
- **Hexadecimal**: `0x` or `0X` (e.g., `0xFF` is 255)

```python
x = 0xFF 
print(x) # Output: 255
```

---

## 2. Floating Point Numbers (`float`)

Python's `float` type is implemented using `double` in C, which follows the **IEEE 754** standard for double precision.

### Precision Caveats:
Because computers use binary to represent decimal fractions, some numbers cannot be represented exactly.
- **Example**: `0.1 + 0.2` is not exactly `0.3` in Python because of hardware limitations.
- **Comparison**: Avoid using `==` with floats. Use `math.isclose()` instead.

### Scientific Notation:
Floats can be written using `e` or `E` to represent powers of 10.
```python
y = 1.5e3  # 1.5 * 10^3 = 1500.0
z = 2e-2   # 2 * 10^-2 = 0.02
```

---

## 3. Complex Numbers (`complex`)

Complex numbers have a real and an imaginary part, denoted by `j` or `J`.

- **Syntax**: `real + imagj`
- **Attributes**: `.real` and `.imag`

```python
c = 3 + 4j
print(c.real) # 3.0
print(c.imag) # 4.0
print(c.conjugate()) # (3-4j)
```

---

## 4. Booleans (`bool`)

Booleans (`True` and `False`) are a subclass of `int`.
- `True` has an integer value of `1`.
- `False` has an integer value of `0`.

```python
print(True + 1) # Output: 2
```

---

## 5. Numeric Operations & Behaviors

### Division:
- **Classic Division (`/`)**: Returns a `float` (e.g., `4 / 2` is `2.0`).
- **Floor Division (`//`)**: Returns an `int` (or float if inputs are float), truncating the fractional part towards negative infinity.
- **Modulo (`%`)**: Returns the remainder.

```python
print(10 / 3)   # 3.3333333333333335
print(10 // 3)  # 3
print(-10 // 3) # -4 (Floors towards negative infinity)
```

### Power Operator:
Use `**` for exponentiation (e.g., `2 ** 3` is `8`).

---

## 6. Precision Modules

When exact precision is required (e.g., in financial applications), Python provides specialized modules.

### `decimal` Module:
Provides fast correctly-rounded decimal floating point arithmetic.
```python
from decimal import Decimal
print(Decimal('0.1') + Decimal('0.2')) # Exactly 0.3
```

### `fractions` Module:
Handles rational numbers without precision loss.
```python
from fractions import Fraction
f = Fraction(1, 3) # Represents exactly 1/3
```

---

## 7. Useful Built-in Functions & `math` Module

### Built-ins:
- `abs(x)`: Absolute value.
- `round(x, n)`: Rounds to `n` digits.
- `pow(x, y)`: Same as `x ** y`.
- `int()`, `float()`, `complex()`: Type conversion.

### The `math` Module:
Standard mathematical constants and functions.
- `math.pi`, `math.e`
- `math.sqrt()`, `math.floor()`, `math.ceil()`
- `math.trunc()`: Truncates towards zero.
- `math.isclose()`: Recommended for float comparisons.