# Lab 4a

## Basic Info
- Author: Aadarsh Devi
- Submission Date: Mar 1, 2026
- Assignment: Lab 4a

## Question 1: Exercising tuples
1. Take five inputs from an user and save it in a tuple called `my_tuple`
```python
userNum1: int = int(input("Enter number 1: "))
userNum2: int = int(input("Enter number 2: "))
userNum3: int = int(input("Enter number 3: "))
userNum4: int = int(input("Enter number 4: "))
userNum5: int = int(input("Enter number 5: "))

my_tuple = (userNum1, userNum2, userNum3, userNum4, userNum5) # type : tuple[int, int, int, int, int]

print(userNum1, userNum2, userNum3, userNum4, userNum5, sep="\t")
print(my_tuple)
```
Output
```
Enter number 1: 7
Enter number 2: 38
Enter number 3: 23
Enter number 4: 89
Enter number 5: 34
7	38	23	89	34
(7, 38, 23, 89, 34)
```

2. How do you assign a single element in a tuple?
```python
userInputNum: int = int(input("Enter a number: "))
singleTuple: tuple[int] = (userInputNum,)
print(singleTuple)
```
Output
```
Enter a number: 27
(27,)
```

3. `my_tuple = (1,2,3,4,3,2,1,2,3,5,4,3,2,1)` Count the repeated integers and print the result on the console.

I tried my best to write the code. I had a hard time writing it.
```python
my_tuple = (1,2,3,4,3,2,1,2,3,5,4,3,2,1)
print("tuple:",my_tuple)

# Contains a list of numbers
numbers: list[int] = [my_tuple[0]]

# List of unique numbers
for number in my_tuple:
    exists: bool = False
    for num in numbers:
        if number == num:
            exists = True
            break
    if not exists:
        numbers.append(number)
print("numbers:",numbers, end="\n\n")

# Frequency of the numbers (Really slow)
frequency = []
for num in numbers:
    freq: int = 0
    for number in my_tuple:
        if number == num:
            freq += 1
    frequency.append(freq)
    print("num", num, "\t- freq:", freq)
    pass
```
Output
```
tuple: (1, 2, 3, 4, 3, 2, 1, 2, 3, 5, 4, 3, 2, 1)
numbers: [1, 2, 3, 4, 5]

num 1 	- freq: 3
num 2 	- freq: 4
num 3 	- freq: 4
num 4 	- freq: 2
num 5 	- freq: 1
```

4. `my_tuple = my_tuple + my_tuple`
```python
my_tuple = (1,2,3,4,3,2,1,2,3,5,4,3,2,1)
my_tuple = my_tuple + my_tuple
print(my_tuple)
```
Output
```
(1, 2, 3, 4, 3, 2, 1, 2, 3, 5, 4, 3, 2, 1, 1, 2, 3, 4, 3, 2, 1, 2, 3, 5, 4, 3, 2, 1)
```

## Question 2: Packing and unpacking tuples
1.
```python
```
Output
```
(1, 2, 3, 4, 3, 2, 1, 2, 3, 5, 4, 3, 2, 1, 1, 2, 3, 4, 3, 2, 1, 2, 3, 5, 4, 3, 2, 1)
```

