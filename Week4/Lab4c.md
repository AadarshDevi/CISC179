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

2. How would you write a function that could take any number of unnamed arguments and print their values out in reverse order?
```python
def reverse(inputs: list) -> list:
    newReversedList: list = []
    for i in range(len(inputs), 0, -1):
        newReversedList.append(inputs[i - 1])
    return newReversedList

running: bool = True
userInputs: list = []

while running:
    userInput: str = input("Please enter a word (type \"n\" to exit): ")
    if userInput == "n":
        running = False
    else:
        userInputs.append(userInput)

if len(userInputs) > 1:
    print("Original:", userInputs)

    reversedList: list = reverse(userInputs)
    print("Reversed:", reversedList)
```
Output:
```
Please enter a word (type "n" to exit): dog
Please enter a word (type "n" to exit): vcat
Please enter a word (type "n" to exit): vegas
Please enter a word (type "n" to exit): cool cat
Please enter a word (type "n" to exit): fluffy
Please enter a word (type "n" to exit): parrot
Please enter a word (type "n" to exit): fish
Please enter a word (type "n" to exit): tortois
Please enter a word (type "n" to exit): turtle
Please enter a word (type "n" to exit): n
Original: ['dog', 'vcat', 'vegas', 'cool cat', 'fluffy', 'parrot', 'fish', 'tortois', 'turtle']
Reversed: ['turtle', 'tortois', 'fish', 'parrot', 'fluffy', 'cool cat', 'vegas', 'vcat', 'dog']
```

3. What would be the result of changing a list or dictionary that was passed into a function as a parameter value? Which operations would be likely to create changes that would be visible outside the function? What steps might you take to minimize that risk?

When a list or dict is used as a param, it is sending a referenced of the object. So when the function does any changes, it affects the list/dict that was the input.

```python
alist: list = ["Tomato", "Orange", "Apple", "Onion", "Watermelon", "Tea Leaf"]
print("unedited:",alist)

def changeList(inputList: list):
    inputList.remove("Orange")
    inputList.append("Pineapple")

changeList(alist)
print("edited:",alist)
```
Output:
```
unedited: ['Tomato', 'Orange', 'Apple', 'Onion', 'Watermelon', 'Tea Leaf']
edited: ['Tomato', 'Apple', 'Onion', 'Watermelon', 'Tea Leaf', 'Pineapple']
```

To fix this problem, we need to create a new list/dict based on the param. Input is a list so the new object will be a list.

```python
alist: list = ["Tomato", "Orange", "Apple", "Onion", "Watermelon", "Tea Leaf"]
print("alist:",alist)

def unchangeableList(inputList: list) -> list:
    outputList: list = list(inputList)
    outputList.remove("Orange")
    outputList.append("Pineapple")
    return outputList

newList: list = unchangeableList(alist)
print("after alist:",alist)
print("newList:",newList)
```
Output:
```
alist: ['Tomato', 'Orange', 'Apple', 'Onion', 'Watermelon', 'Tea Leaf']
after alist: ['Tomato', 'Orange', 'Apple', 'Onion', 'Watermelon', 'Tea Leaf']
newList: ['Tomato', 'Apple', 'Onion', 'Watermelon', 'Tea Leaf', 'Pineapple']
```

By creating a new list from the old list, we are now changing the new list and not accidentally changing the old list.

# Challenges
1. Writing algorithms for Q 1a. I had a hard time trying to figure out string methods.
2. 
