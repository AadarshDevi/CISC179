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


## What to Submit
1. Python File(s): [Python File](Printing.py)
2. Drawio Flowchart: [Draw.io Flowchart](Lab_2a_flowchart.drawio)
3. Flowchart as Image: [Draw.io Image](Lab_2a_flowchart_image.png)
4. Challenges:
    1. Trying to understand something like print() has so much versitility.
    2. Lot of experimenting needed to understand what this simepple method did.
