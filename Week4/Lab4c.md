# Lab 4c: Functions

## Basic Info
- Author: Aadarsh Devi
- Submission Date: Mar 1, 2026
- Assignment: Lab 4a

## Question 1: Unit Convertor

1. The user selects kilometers per liter (kpl), and the response will be provided in miles per gallon (mpg). The units must be interchangeable, so the program will ask the user whether to convert from kpl to mpg or vice versa. The program will prompt the user for input and deliver output with the appropriate units. Additionally, the program will include input validation. For example, it will not accept letter inputs and will provide an error message to the user when invalid input is detected. The function will also allow multiple arguments, enabling the user to convert multiple values at once. Research and find out the conversion factor between the units.

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

4. Assuming that x = 5, what will be the value of x after funct_1() below executes? After funct_2() executes?

The python code would look like this, so we can know what the actual ans is after theorizing.
```python
x = 5
print("x1:",x)

def funct_1():
  x=3

def funct_2():
  global x
  x=2

funct_1()
print("x2:",x)
funct_2()
print("x3:",x)
```

First we have `x = 5` which means x has a value 5. next we are calling `func_1()`. `func_1()` has a local variable `x` but it is not the same `x` that is above the function header. so when this is run, x will remain to have a value of 5.

After running `func_1()`, we run `func_2()`. when we run, we have `global x`. `global x` here is refering to `x = 5` so when we goto the next statement `x = 2`, we are changing the value of x from 5 to 2. Now to test the theory.

Output:
```
x1: 5
x2: 5
x3: 2
```

By running the code, we can see that `func_1()` did not change `x` and `func_2()` changed `x` from 5 to 2.

## Question 2: Troubleshooting

1. Correct the following code. There might be more than one correct answers. Explain your reasoning.

Below is the given code.
```python
def my_func(a,b,**c):
  print(c)

my_func(1,2,3,4,5,6)
```

2. Using the following code, x should print 100 but it prints 10, why?

Below is the given code.
```python
def my_func_global():
  x = 100

global x
x = 10
my_func_global()
print(x)
```



# Challenges
1. Writing algorithms for Q 1a. I had a hard time trying to figure out string methods.
2. 
