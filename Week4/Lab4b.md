# Lab 4b: Dictionary

## Basic Info
- Author: Aadarsh Devi
- Submission Date: Mar 1, 2026
- Assignment: Lab 4a

## Question1: Creating and accessing dictionary

1. Create dictionary of your choice of keys and values. Create dictionary size of 10 elements.
```python
# A dictionary of movies and their animation company
moviesAndCompanies = {
    "Next_Gen": "Netflix",
    "The_Lion_King": "Disney",
    "The_Bad_Guys": "DreamWorks",
    "Spiderman_Into_the_Spider_verse": "Sony",
    "Spies_In_Disguise": "Blue_Sky_Studios",
    "Ratatouille": "Pixar",
    "Cars_3": "Pixar",
    "The_Super_Mario_Bros_Movie": "Nintendo",
    "Minions": "Illumination",
    "Ice_Age": "Blue_Sky_Studios"
}
```

2. Take inputs from a user and add them in a dictionary called `my_user_dict`
```python
running: bool = True
studentIdAndName: dict = {}

while running:
    ssn: str = input("SSN: ")
    name: str = input("Name: ")
    ans: str = input("Do you want to continue (Y/N) ")
    studentIdAndName.update({ssn: name})
    if ans.upper().startswith("N"):
        running = False

print(studentIdAndName)
```

3. Based on the given tuple, create a code which checks for valid key & value pairs, and check for key duplication. The code should provide assistance to a user to correct the error. For key duplication, ask user to change the key.
```python

```




# Challenges
1. Writing the frequency of the numbers was hard. I was struggling to get a good algorithm.
2. the `*` and `**` were okay, but i need to read and understand it better.
3. The exam on tuples, dict, functions, loops was hard. I needed more practice.
