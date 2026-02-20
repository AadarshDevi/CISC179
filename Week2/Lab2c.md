# Lab 2c

## Basic Info
- Author: Aadarsh Devi
- Submission Date: Feb 2, 2026
- Assignment: Lab 2a

## Variable Memeory Usage
```python
var1 = 20
var1 = 100
```
| Code | Memeory Address |
|:------:|:---------:|
| `var1 = 20` | 0x7ffa2d8f76d8 |
| `var1 = 100` | 0x7ffa2d8f80d8 |

There are 2 memeory addresses because there are 2 different distainct values.

## Memory Map
```python
str1 = "Hello"
str2 = "World"

print(hex(id(str1[0])), hex(id(str2[0])), sep="\t\t")
print(hex(id(str1[1])), hex(id(str2[1])), sep="\t\t")
print(hex(id(str1[2])), hex(id(str2[2])), sep="\t\t")
print(hex(id(str1[3])), hex(id(str2[3])), sep="\t\t")
print(hex(id(str1[4])), hex(id(str2[4])), sep="\t\t")
```
| Letter | Memeory Address |
|:------:|:---------:|
| H | 0x7ffa2d907448 |
| e | 0x7ffa2d9079b8 |
| l | 0x7ffa2d907b08 |
| l | 0x7ffa2d907b08 |
| o | 0x7ffa2d907b98 |
| W | 0x7ffa2d907718 |
| o | 0x7ffa2d907b98 |
| r | 0x7ffa2d907c28 |
| l | 0x7ffa2d907b08 |
| d | 0x7ffa2d907988 |

## Problem-solving
No python code run.
```python
x: str = "dog"
y: str = "cat"

print(x + y)
print("the " + x + " chases the " + y)
print(x * 4)
```
Output:
```
dogcat
the dog chases the cat
dogdogdogdog
```

## Troubleshooting
Questions:
1. `hello = "hello"`: There is no problem found
2. `_var = 100`: There is no problem found
3. `!var_1 = 200`: starts with an "!"
4. `print = "print me"`: There is no problem found
5. `False = 0`: The name of the variable is a python keyword

## Challenges
1. Troubleshooting was taking some time. Some of them, I think were fine with no problems.
