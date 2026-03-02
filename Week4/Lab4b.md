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
Code is not fully implemented. It is also broken.
```python
a = [("a", 1), ("b", 2), ("c", 3), ("a", 1), ("b", 2), ("c", 3)]
l: list = [] # list

for key, val in a:
    print("kv:", key, val)
    if len(l) == 0:
        l.append(key)
        print("ll:",l)
        continue
    unique: bool = True
    for uniKey in l: # uniKey = unique key
        print("uk:",uniKey)
        if key == uniKey:
            print("duplicate:",key)
            unique = False
    while not unique:
        print(unique)
        newKey: str = input("New Key: ")
        newUnique = True
        for uniKey in l:  # uniKey = unique key
            print("uk:", uniKey)
            if newKey == uniKey:
                newUnique = False
        if newUnique:
            l.append(newKey)
    if unique:
        l.append(key)
    print("lll:", l)
print(l)
print(a)
```

4. Convert the following list into a dictionary. Automate the process by using the loop.
```python
personInfo = [('Name', 'Sarah Connor'), ('Date of birth', '1 Jan 1980'), ('Address', '1000 Black Mountain Drive', 92126), ('Name', 'Jim Hawkins')]
personDict: dict = {}
for personField in personInfo:
    #                   Key: Value
    personDict.update({personField[0]: personField[1]})
print(personDict)
```

5. Use the following text and count the number of words using dictionary. Remember The or the counts as 2.


Input Scentence:
```
The tiger (Panthera tigris) is a large cat and a member of the genus Panthera native to Asia. It has a powerful, muscular body with a large head and paws, a long tail and orange fur with black, mostly vertical stripes. It is traditionally classified into nine recent subspecies, though some recognise only two subspecies, mainland Asian tigers and the island tigers of the Sunda Islands.
```
Code:
```python
sentence: str = "The tiger (Panthera tigris) is a large cat and a member of the genus Panthera native to Asia. It has a powerful, muscular body with a large head and paws, a long tail and orange fur with black, mostly vertical stripes. It is traditionally classified into nine recent subspecies, though some recognise only two subspecies, mainland Asian tigers and the island tigers of the Sunda Islands."
words: list[str] = sentence.split(" ")
frequency: dict = {}

for word in words:
    word = word.lower().replace(".", "").replace("(", "").replace(")", "").replace(",", "")
    # print(word)
    if word not in frequency:
        frequency[word] = 1
    else:
        frequency[word] += 1

for key, value in frequency.items():
    print("word: \"",key, "\"\t\tfreq: ", value, sep="")
```
Output:
```
word: "the"		freq: 4
word: "tiger"		freq: 1
word: "panthera"		freq: 2
word: "tigris"		freq: 1
word: "is"		freq: 2
word: "a"		freq: 5
word: "large"		freq: 2
word: "cat"		freq: 1
word: "and"		freq: 4
word: "member"		freq: 1
word: "of"		freq: 2
word: "genus"		freq: 1
word: "native"		freq: 1
word: "to"		freq: 1
word: "asia"		freq: 1
word: "it"		freq: 2
word: "has"		freq: 1
word: "powerful"		freq: 1
word: "muscular"		freq: 1
word: "body"		freq: 1
word: "with"		freq: 2
word: "head"		freq: 1
word: "paws"		freq: 1
word: "long"		freq: 1
word: "tail"		freq: 1
word: "orange"		freq: 1
word: "fur"		freq: 1
word: "black"		freq: 1
word: "mostly"		freq: 1
word: "vertical"		freq: 1
word: "stripes"		freq: 1
word: "traditionally"		freq: 1
word: "classified"		freq: 1
word: "into"		freq: 1
word: "nine"		freq: 1
word: "recent"		freq: 1
word: "subspecies"		freq: 2
word: "though"		freq: 1
word: "some"		freq: 1
word: "recognise"		freq: 1
word: "only"		freq: 1
word: "two"		freq: 1
word: "mainland"		freq: 1
word: "asian"		freq: 1
word: "tigers"		freq: 2
word: "island"		freq: 1
word: "sunda"		freq: 1
word: "islands"		freq: 1
```


# Challenges
1. Writing the frequency of the numbers was hard. I was struggling to get a good algorithm.
2. the `*` and `**` were okay, but i need to read and understand it better.
3. The exam on tuples, dict, functions, loops was hard. I needed more practice.
