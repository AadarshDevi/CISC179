# Lab 2d

## Basic Info
- Author: Aadarsh Devi
- Submission Date: Feb 2, 2026
- Assignment: Lab 2d

## User Input
A.
  ```python
  weightKg: float = float(input("Enter your weight (kg): "))
  weightLb: float = weightKg * 2.2;
  print("Your weight in lb is", weightLb)
  ```
B.
  ```python
  netBalance: float = float(input("Enter Balance on Bill: ")) # balance shown on bill
  payment: float = float(input("Enter Payment paid: ")) # payment made
  d1: int = int(input("Enter Days for Billing Cycle: ")) # days for billing cycle
  d2: int = int(input("No. of Days Payment made before Billing Cycle: ")) # payment done before billing cycle
  interestPerMonth: float = float(input("Enter Interest per Month: "))
  
  averageDailyBalance: float = (netBalance * d1 - payment * d2) / d1
  interest: float = averageDailyBalance * interestPerMonth
  
  print("Interest is", interest)
  ```
C.
  ```python
  x: float = float(input("Average Speed of Car A (mph): ")) # Speed of car a
  y: float = float(input("Average Speed of Car B (mph): ")) # Speed of car b
  
  carATimeHrs: float = float(input("Time Car A left center (hrs): "))
  carATimeMin: float = float(input("Time Car A left center (min): "))
  
  carBTimeHrs: float = float(input("Time Car B left center (hrs): "))
  carBTimeMin: float = float(input("Time Car B left center (min): "))
  
  # Pythagoras Theorem
  shortestDistance: float = ((carATimeHrs + (carATimeMin / 60.0)) ** 2 + (carBTimeHrs + (carBTimeMin / 60.0)) ** 2) ** 0.5
  print("Shortest distance between Car A and Car B is", shortestDistance, "miles.")
  ```


## Challenges
1.
