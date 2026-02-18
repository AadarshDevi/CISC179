# Lab 2b: Python Literals

# Python Precedence

Top to bottom from left to right.
```
**          # only a group of this is right - left
+/-ve
* / % //
+ -
```

# 1. Literals

```python
print(5 + 2 - 2) # 1
print(5 / 2) # 2
print(6 // 2) # 3

print(2. * 3) # 4
print(2 < 4) # 5
print(2 >= 2) # 6

print("Hello"+"World") # 7
print("bla" * 3) # 8
print(2 * 3 ** 3) # 9

print(5 * 25 // 13 + 100 / 2 % 13 // 2) # 10
print(2 * 3 % 5)  # 11
print((2 % -4), (2 % 4), (2 ** 3 ** 2)) # 12
```

## **_Answers:_** My Calculations
```python
5 # 1
2.5 # 2
3 # 3

6.0 # 4
True # 5
True # 6

HelloWorld # 7
blablaba # 8
```
```
Question 9:

2 * 3 ** 3
= 2 * (3 ** 3)
= 2 * 9
= 512

Answer: 512
---------------------

Question 10:

5 * 25 // 13 + 100 / 2 % 13 // 2
= ((5 * 25) // 13) + 100 / 2 % 13 // 2
= (125 // 13) + 100 / 2 % 13 // 2
= 9 + 100 / 2 % 13 // 2
= 9 + (((100 / 2) % 13) // 2)
= 9 + ((50.0 % 13) // 2)
= 9 + (11 // 2)
= 9 + 5
= 14

Answer: 14
---------------------

Question 11:

2 * 3 % 5
= ((2 * 3) % 5)
= (6 % 5)
= 1

Answer: 1
---------------------

Question 12:

(2 % -4), (2 % 4), (2 ** 3 ** 2)
= (2 % -4), (2 % 4), (2 ** 3 ** 2)
= -2, (2 % 4), (2 ** 3 ** 2)
= -2, 2, (2 ** 3 ** 2)
= -2, 2, (2 ** 3 ** 2)
= -2, 2, ___

in (2 ** 3 ** 2), the exponents go from left to right

= -2, 2, (2 ** 9)
= -2, 2, 512

Answer: -2, 2, 512
```

## Results

| Question | Result | My Answer | Python Answer |
|:--------:|:------:|:---------:|:-------------:|
|     1    |   ✔️   | 5 | 5 |
|     2    |   ✔️   | 2.5 | 2.5 |
|     3    |   ✔️   | 3 | 3 |
|     4    |   ✔️   | 6.0 | 6.0 |
|     5    |   ✔️   | True | True |
|     6    |   ✔️   | True | True |
|     7    |   ✔️   | HelloWorld | HelloWorld |
|     8    |   ✔️   | blablaba | blablaba |
|     9    |   ❌   | 512 | 54 |
|    10    |   ❌   | 14 | 14.0 |
|    11    |   ✔️   | 1 | 1 |
|    12    |   ❌   | -2, 2, 512 | 2 2 512 |

# 2. Data type

```python
type("Hello") # 1
type(1+"2") # 2
type(1.) # 3

type('A') # 4
type(500) # 5
type(True) # 6

type("False") # 7
```

## Answers

1. str
2. str
3. float
4. str
5. int
6. bool
7. str

## Results

| Question | Result | My Answer | Python Answer |
|:--------:|:------:|:---------:|:-------------:|
|     1    |   ✔️   |    str    |      str      |
|     2    |   ❌   |    str    |   TypeError   |
|     3    |   ✔️   |   float   |     float     |
|     4    |   ✔️   |    str    |      str      |
|     5    |   ✔️   |    int    |      int      |
|     6    |   ✔️   |    bool   |      bool     |
|     7    |   ✔️   |    str    |      str      |

# 3. Operator Precedence

Use Exponent (Right --> Left), (Left --> Right from now on) Unary, Multiplication, Division, Integer Division, Modulus, Addition, Subtraction

## Answers

1. Add exponent with a negative power (unary)
```
12 ** 2 = 144.0
```
2. Multiplication then Division on the exponent
```
12 ** 2 * -9 / -3
```
3. add integer division to base and mod it
```
12 ** 2 * -9 / -3 // 4 % 9.5
```
4. now add a value and subtract a value it
```
27.11 - 19.37 + 12 ** 2 * -9 / -3 // 4 % 9.5
```

Now breakdown
```
27.11 - 19.37 + 12 ** 2 * -9 / -3 // 4 % 9.5
= 27.11 - 19.37 + (12 ** 2) * -9 / -3 // 4 % 9.5
= 27.11 - 19.37 + (((((12 ** 2) * -9) / -3) // 4) % 9.5)
= 27.11 - 19.37 + ((((144 * -9) / -3) // 4) % 9.5)
= 27.11 - 19.37 + (((-1296 / -3) // 4) % 9.5)
= 27.11 - 19.37 + ((432.0 // 4) % 9.5)
= 27.11 - 19.37 + (108 % 9.5)
= 27.11 - 19.37 + 3.5
= 11.24
```

## Result

```python
print(27.11 - 19.37 + 12 ** 2 * -9 / -3 // 4 % 9.5)
```
Answer:
```
7.739999999999998
```

