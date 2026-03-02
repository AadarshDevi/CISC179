# Lab 4c: Functions

## Basic Info
- Author: Aadarsh Devi
- Submission Date: Mar 1, 2026
- Assignment: Lab 4a

## Question 1: Unit Convertor

1. 

Code:
```python
def conversion(_unit: str, _value: float) -> float:
    # kpl -> mpg
    if units.lower() == "kpl":
        return  _value * (47.0 / 20.0)

    # mpg -> kpl
    else:
        return  _value * (20.0 / 47.0)


def validInput(uncheckedValue: str) -> bool:
    if not uncheckedValue.replace(".", "").isdigit():
        return False
    return True


def getInputList(unsplitValues: str) -> list:
    splitValues = unsplitValues.split(",")
    for valueStr in splitValues:
        valueStr = valueStr.strip()
    return splitValues


def convert(units, convertedUnit, unconvertedValue):
    floatValue: float = float(unconvertedValue)
    convertedValue: float = conversion(units, floatValue)
    print(floatValue, units, "is", "%.3f" % convertedValue, convertedUnit)

correctUnits: bool = False
units: str = ""

while not correctUnits:
    rawUnits = input("Conversion > From (kpl/mpg): ")
    if rawUnits.lower() == "kpl" or rawUnits.lower() == "mpg":
        units = rawUnits
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

print()
value: str = input("Enter " + units + ": ")
values: list = []
if "," in value:
    values = getInputList(value)
else:
    if not validInput(value):
        quit()
print()

if len(values) <= 1:
    floatValue: float = float(value)
    convertedValue: float = conversion(units, floatValue)
    print(floatValue, units, "is", "%.3f" % convertedValue, convertedUnit)
    quit()


for unconvertedValue in values:
    unconvertedValue = unconvertedValue.replace(" ", "")
    print("value:", "\""+unconvertedValue+"\"")
    if validInput(unconvertedValue):
        convertedValue: float = conversion(units, float(unconvertedValue))
        print(unconvertedValue, units, "is", "%.3f" % convertedValue, convertedUnit)
    else:
        print("Wrong value. It has to be a float or int. value received:", unconvertedValue)
    print()
```
Output 1:
```
Conversion > From (kpl/mpg): kpo
Wrong unit. Enter valid units: kpl, mpg
Conversion > From (kpl/mpg): kpl
Converting from kpl to mpg

Enter kpl: 12.45

12.45 kpl is 29.258 mpg
```
Output 2:
```
Conversion > From (kpl/mpg): kpl
Converting from kpl to mpg

Enter kpl: 12.45, 56, 67, 12.74

value: "12.45"
12.45 kpl is 29.258 mpg

value: "56"
56 kpl is 131.600 mpg

value: "67"
67 kpl is 157.450 mpg

value: "12.74"
12.74 kpl is 29.939 mpg
```


# Challenges
1. 
