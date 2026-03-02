# Lab 4c: Functions

## Basic Info
- Author: Aadarsh Devi
- Submission Date: Mar 1, 2026
- Assignment: Lab 4a

## Question 1: Unit Convertor

1. 

Code:
```python

correctUnits: bool = False
units: str = ""

while not correctUnits:
    _units = input("Conversion > From (kpl/mpg): ")
    if _units.lower() == "kpl" or _units.lower() == "mpg":
        units = _units
        correctUnits = True
    else:
        print("Wrong unit. Enter valid units: kpl, mpg")
        correctUnits = False

convertedUnit: str = ""
if units.lower() == "kpl":
    convertedUnit = "mpg"
else:
    convertedUnit = "kpl"

print("Converting from", units, "to", convertedUnit)

value: float = float(input("Enter " + units + ": "))
convertedValue: float = 0.0

# kpl -> mpg
if units.lower() == "kpl":
    convertedValue = value * (47.0 / 20.0)
else: # mpg -> kpl
    convertedValue = value * (20.0 / 47.0)

print(value, units, "is", "%.3f" % convertedValue, convertedUnit)
```
Output 1:
```
Conversion > From (kpl/mpg): rtx
Wrong unit. Enter valid units: kpl, mpg
Conversion > From (kpl/mpg): kpl
Converting from kpl to mpg

Enter kpl: 12.34, 45,56, 99.23
"12.34"
"45"
"56"
"99.23"

value: "12.34"
validate: 1234
12.34 kpl is 28.999 mpg

value: "45"
validate: 45
45 kpl is 105.750 mpg

value: "56"
validate: 56
56 kpl is 131.600 mpg

value: "99.23"
validate: 9923
99.23 kpl is 233.191 mpg
```
Output 2:
```
Conversion > From (kpl/mpg): kpl
Converting from kpl to mpg

Enter kpl: 57.62
validate: 5762

57.62 kpl is 135.407 mpg
```


# Challenges
1. 
