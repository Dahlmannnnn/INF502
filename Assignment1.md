Question 1:

Example runs:

    Please input length of side a: 2
    Please input length of side b: 2
    
    Length of side c is:  2.8284271247461903
    

    Please input length of side a: 3
    Please input length of side b: 4
    
    Length of side c is:  5.0
    

    Please input length of side a: 7
    Please input length of side b: 8
    
    Length of side c is:  10.63014581273465
    

```python

def pythagoreanTheorem(length_a, length_b):
  Length_c = (length_a**2 + length_b**2)**0.5
  return Length_c

a = float(input("Please input length of side a: "))
b = float(input("Please input length of side b: "))

c = pythagoreanTheorem(a,b)

print("Length of side c is: ", str(c))

```

Question 2:

The idea behind this is to have the list enter a while loop that checks each element in the list via an if else statement and applies the correct multiplication. Additionally, I have the user define how long the list is before inputting values.

Example runs:

    Enter number of elements: 5
    Please enter a value in the list: 1
    Please enter a value in the list: 2
    Please enter a value in the list: 3
    Please enter a value in the list: 4
    Please enter a value in the list: 5
    
    [3, 4, 9, 8, 15]
    

    Enter number of elements: 12
    Please enter a value in the list: 2
    Please enter a value in the list: 5
    Please enter a value in the list: 3
    Please enter a value in the list: 6
    Please enter a value in the list: 12
    Please enter a value in the list: 28
    Please enter a value in the list: 33
    Please enter a value in the list: 36
    Please enter a value in the list: 89
    Please enter a value in the list: 8
    Please enter a value in the list: 2
    Please enter a value in the list: 3
    
    [4, 15, 9, 12, 24, 56, 99, 72, 267, 16, 4, 9]
    

    Enter number of elements: 3
    Please enter a value in the list: 1
    Please enter a value in the list: 2
    Please enter a value in the list: 3
    
    [3, 4, 9]


```python

def list_mangler(list_in):
  element = 0
  while element < len(list_in):
    if list_in[element]%2 == 0:
      list_in[element] = list_in[element]*2
    else:
      list_in[element] = list_in[element]*3
    element = element+1
  return list_in

lst = []
n = int(input("Enter number of elements: "))
for i in range(0, n): 
    ele = int(input("Please enter a value in the list: ")) 
    lst.append(ele)


lst_man = list_mangler(lst)

print(str(lst_man))

```

Question 3:

This code works by having the user input the number of grades, the grades themselves (put into a list), and then the number to be dropped. Then it sorts the list and creates a new one that starts after the number to be dropped and finds the average of the new list. Then it runs in an if starement to find the letter grade to be printed.

Example runs:

    Enter number of grades: 5
    Please enter a grade: 20
    Please enter a grade: 100
    Please enter a grade: 60
    Please enter a grade: 90
    Please enter a grade: 90
    Please enter the number of dropped grades:2
    
    Final letter grade is  A
    

    Enter number of grades: 5
    Please enter a grade: 20
    Please enter a grade: 30
    Please enter a grade: 40
    Please enter a grade: 60
    Please enter a grade: 100
    Please enter the number of dropped grades:2
    
    Final letter grade is  B
    

    Enter number of grades: 4
    Please enter a grade: 100
    Please enter a grade: 90
    Please enter a grade: 95
    Please enter a grade: 80
    Please enter the number of dropped grades:2
    
    Final letter grade is  A

```python

def grade_calc(grades_in, to_drop):
  grades_in.sort()
  
  grade = grades_in[to_drop+1:]
  s = sum(grade)
  
  gr = s/len(grade)
  if gr>=90:
    letter = 'A'
  elif gr>=80:
    letter = 'B'
  elif gr>= 70:
    letter = 'C'
  elif gr>= 60:
    letter = 'D'
  else:
    letter = 'F'
  return letter

lst = []
n = int(input("Enter number of grades: "))
for i in range(0, n): 
    ele = int(input("Please enter a grade: ")) 
    lst.append(ele)
drop = int(input("Please enter the number of dropped grades:"))


grade = grade_calc(lst, drop)

print("Final letter grade is ", grade)

```

Question 4:

This code prompts the user to input the number of elements in a list followed by the list itself, then it enters a while loop and a nested if statement to determine if each element is even or odd and then sorts into two new lists that are used as inputs to a list that is returned.

Example runs:

    Enter number of elements in list: 5
    Please enter a value in list: 1
    Please enter a value in list: 2
    Please enter a value in list: 3
    Please enter a value in list: 4
    Please enter a value in list: 5
    
    [[1, 3, 5], [2, 4]]
    

    Enter number of elements in list: 8
    Please enter a value in list: 2
    Please enter a value in list: 4
    Please enter a value in list: 6
    Please enter a value in list: 8
    Please enter a value in list: 10
    Please enter a value in list: 12
    Please enter a value in list: 14
    Please enter a value in list: 3
    
    [[3], [2, 4, 6, 8, 10, 12, 14]]
    

    Enter number of elements in list: 8
    Please enter a value in list: 3
    Please enter a value in list: 5
    Please enter a value in list: 9
    Please enter a value in list: 11
    Please enter a value in list: 13
    Please enter a value in list: 2
    Please enter a value in list: 15
    Please enter a value in list: 17
    
    [[3, 5, 9, 11, 13, 15, 17], [2]]

```python

def odd_even_filter(numbers):
  pos_even=0
  pos_odd=0
  evens = []
  odds = []
  element = 0
  while element < len(numbers):
    if numbers[element]%2 == 0:
      evens.insert(pos_even, numbers[element])
      pos_even = pos_even+1
    else:
      odds.insert(pos_odd, numbers[element])
      pos_odd = pos_odd + 1
    element = element+1
  lst=[odds, evens]
  return lst

lst = []
n = int(input("Enter number of elements in list: "))
for i in range(0, n): 
    ele = int(input("Please enter a value in list: ")) 
    lst.append(ele)


lst_srt = odd_even_filter(lst)

print(str(lst_srt))

```
