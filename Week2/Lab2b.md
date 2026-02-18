# Lab 2b: Python Literals

# Python Precedence

Top to bottom from left to right.
```
**
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

## **_Answers:_**
```python
5 # 1
2.5 # 2
2 # 3

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

Answer: 
```
