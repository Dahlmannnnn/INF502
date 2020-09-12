Question 1:
```python

lst=[]
for i in range(0, 5): 
    ele = int(input("Please enter money in a wallet: ")) 
    lst.append(ele)

lst.sort()

print("The fattest wallet has $",str(lst[4]),"in it")
print("The skinniest wallet has $",str(lst[0]),"in it")
print("All together the wallets have $",str(sum(lst)),"in them")
print("All together the wallets have",str(sum(lst)*10)," dimes in them")

```


Question 2:
```python
w = 0
Table = { "H": {"Symbol":"H", "Name":"Hydrogen", "Number":1, "Row":1, "Column":1},
"He": {"Symbol":"He", "Name":"Helium", "Number":2, "Row":1, "Column":18},
"Li": {"Symbol":"Li", "Name":"Lithium", "Number":3, "Row":2, "Column":1},
"Be": {"Symbol":"Be", "Name":"Beryllium", "Number":4, "Row":2, "Column":2},
"B": {"Symbol":"B", "Name":"Boron", "Number":5, "Row":2, "Column":13},
"C": {"Symbol":"C", "Name":"Carbon", "Number":6, "Row":2, "Column":14},
"N": {"Symbol":"N", "Name":"Nitrogen", "Number":7, "Row":2, "Column":15},
"O": {"Symbol":"O", "Name":"Oxygen", "Number":8, "Row":2, "Column":16},
"F": {"Symbol":"F", "Name":"Florine", "Number":9, "Row":2, "Column":17},
"Ne": {"Symbol":"Ne", "Name":"Neon", "Number":10, "Row":2, "Column":18},
"Na": {"Symbol":"Na", "Name":"Sodium", "Number":11, "Row":3, "Column":1},
"Mg": {"Symbol":"Mg", "Name":"Magnesium", "Number":12, "Row":3, "Column":2},
"Al": {"Symbol":"Al", "Name":"Aluminum", "Number":13, "Row":3, "Column":13},
"Si": {"Symbol":"Si", "Name":"Silicon", "Number":14, "Row":3, "Column":14},
"P": {"Symbol":"P", "Name":"Phosphorus", "Number":15, "Row":3, "Column":15},
"S": {"Symbol":"S", "Name":"Sulfer", "Number":16, "Row":3, "Column":16},
"Cl": {"Symbol":"Cl", "Name":"Chlorine", "Number":17, "Row":3, "Column":17},
"Ar": {"Symbol":"Ar", "Name":"Argon", "Number":18, "Row":3, "Column":18}}

while w<1:
  print("Menu\n")
  print("[1] See stored data")
  print("[2] Sort by property")
  print("[3] Enter new element")
  print("[4] Edit element")
  print("[5] Exit\n")

  s = int(input("Please enter your selection: "))

  if s == 1:
    sym = input("Please enter element symbol:")
    print(Table[sym])
  
  elif s == 2:
    print("Display: \n")
    print("[1] Row")
    print("[2] Column")
    print("[3] Atomic Number")
    print("[4] Name")


    d = int(input("Please enter your selection: "))

    if d == 1:
      for x in Table:
        print (x)
        print ('Row:',Table[x]['Row'])


    elif d == 2:
      for x in Table:
        print (x)
        print ('Column:',Table[x]['Column'])

    elif d == 3:
      for x in Table:
        print (x)
        print ('Atomic Number:',Table[x]['Number'])

    elif d == 4:
      for x in Table:
        print (x)
        print ('Name:',Table[x]['Name'])       
    
  elif s == 3:
    sym = input("Please enter element symbol:")
    nm = input("Please enter element name: ")
    nu = int(input("Please enter atomic number of element: "))
    rw = int(input("Please enter periodic table row: "))
    col = int(input("Please enter periodic table column: "))
    l = {"Symbol":sym, "Name":nm, "Number":nu, "Row":rw, "Column":col}

    Table[sym] = l

  elif s == 4:
    sym = input("Please enter element symbol:")
    print(Table[sym])
    nm = input("Please enter element name: ")
    nu = int(input("Please enter atomic number of element: "))
    rw = int(input("Please enter periodic table row: "))
    col = int(input("Please enter periodic table column: "))
    l = {"Name":nm, "Number":nu, "Row":rw, "Column":col}

    Table[sym] = l

  elif s == 5:
    break
 
  else:
    print("Invalid Input\n")

```
