## Igor Feedback

* Overall: It works! Some issues: The string read from the file is not trimmed (strip()), therefore, an extra character is read when there is a line break. Not checking chars different than ACTG. Lengths are checked (but adjusted); the assignment required to check and return an error. Code is not well structured in functions.

* Number of matches: Correct (but there is a need to strip when /n is there)
* Maximum chain: Correct (but there is a need to strip when /n is there)
* User-input: OK
* Max Shift: OK. 
* Exception handling/checks: Not good. Checking some things missing others
    - Files: OK...But context is missing + I cannot retry
    - Conversions: OK.
    - Inputs: OK... 
    - same size, no bad chars, etc.:  No check for chars that are not ACTG; Length is checked but fixed instead of raised as error.
* Functions: A few. The core ones are not structured as functions

* Variable + function names: No... not easily understandable

* **Your grade is 78/100**


I decided to write this program by starting with the functions to determine both the pairs and contiguous requiring the inputs of both the lists and the length of the lists.
Then a file input system is implemented where an individual needs to input the name of a file minus the .txt at the end (ie if the file is called "file1.txt", the user only inputs "file1")
The files are checked if they exist and then puts the contents into two lists for easy analysis. 
Then the file asks for what shifting needs to happen as well as what output they want. Both are done using while and if statements.


```python

def ser (a,b,c):
  inde = 0
  tally = 0
  while inde < c: 
    if a[inde] == b[inde]:
      tally = tally + 1
    inde = inde + 1
  return tally
          
def conge (a,b,c):
  inde = 0
  tally = 0
  maxtal = 0
  an = a[:]
  bn = b[:]
  an.append(0)
  bn.append(0)
  while inde < c:
    if an[inde] == bn[inde] and an[inde] != '0':
      tally = tally + 1
      if tally > maxtal:
       
        maxtal = tally
    
    else:
      tally = 0

    inde = inde + 1
  return maxtal


str1 = []
str2 = []
flg=0
while flg == 0: 
    try:
        F1 = input("Please state the first file to be used: ")
        file_handler = open('%s.txt' % F1, 'r')
        
    except:
        print("File does not exist \n")
        
    else:
        flg=1
        
while 1:
    char = file_handler.read(1)
    if not char:
        break
    str1.append(char)
           
       
file_handler.close()    
    
while flg == 1: 
    try:
        F2 = input("Please state the second file to be used: ")
        file_handler = open('%s.txt' % F2, 'r')
        
    except:
        print("File does not exist \n")
        
    else:
        flg=2

while 1:
    char = file_handler.read(1)
    if not char:
        break
    str2.append(char)
        
        
file_handler.close()   

print("\n Menu")
print("\n 1: Display total matching pairs. \n")
print("\n 2: Display total contiguous pairs. \n")
print("\n 3: Display Both. \n")

while 1:
  try:
    sele = int(input("Please make your selection: "))
  except:
    print("Not an Integer \n")
  else:
    print("\n")
    break

ls1 = len(str1)
ls2 = len(str2)

while ls1 != ls2:
  if ls1 > ls2:
    str2.append('0')
  elif ls2 > ls1:
    str1.append('0')
  ls1 = len(str1)
  ls2 = len(str2)

leng = len(str1)    

while 1:
  try:
    shift = int(input("Please enter the maximum shift: "))
  except:
    print("Not an Integer \n")
  else:
    print("\n")
    break


match = []
cong = []
str1n = []
str2n = []

match.append(ser (str1, str2, leng))
cong.append(conge (str1, str2, leng))
print(str1)
print(str2)
if sele == 1:
  print("No shifting provides " + str(match[0]) + " matche(s) \n")
  
elif sele == 2:
  print("No shifting provides " + str(cong[0]) + " contiguous. \n")

elif sele == 3:
  print("No shifting provides " + str(match[0]) + " matche(s) and " + str(cong[0]) + " contiguous. \n")

shifted = 0
str1n.extend(str1)
str2n.extend(str2)
lengn = leng


while shifted < shift:  
  str1n.insert(0,'0')
  lengn = leng+1
  str2n.append('0')
  print(str1n)
  print(str2n)
  match.append(ser (str1n, str2n, lengn))
  cong.append(conge (str1n, str2n, lengn))
  if sele == 1:
    print("The first list shifted by " + str(shifted+1) + " has " + str(match[shifted+1]) + " matche(s) \n")

  elif sele == 2:
    print("The first list shifted by " + str(shifted+1) + " has " + str(cong[shifted+1]) + " contiguous. \n")

  elif sele ==3:    
    print("The first list shifted by " + str(shifted+1) + " has " + str(match[shifted+1]) + " matche(s) and " + str(cong[shifted+1]) + " contiguous. \n")
  shifted = shifted + 1

shifted = 0

str1n = str1[:]
str2n = str2[:]

lengn = leng

while shifted < shift:  
  str2n.insert(0,'0')
  lengn = leng+1
  str1n.append('0')
  print(str1n)
  print(str2n)
  match.append(ser (str1n, str2n, lengn))
  cong.append(conge (str1n, str2n, lengn))

  if sele == 1:
    print("The second list shifted by " + str(shifted+1) + " has " + str(match[shifted+shift+1]) + " matche(s) \n")

  elif sele == 2:
    print("The second list shifted by " + str(shifted+1) + " has " + str(cong[shifted+shift+1]) + " contiguous. \n")

  elif sele == 3:    
    print("The second list shifted by " + str(shifted+1) + " has " + str(match[shifted+shift+1]) + " matche(s) and " + str(cong[shifted+shift+1]) + " contiguous. \n")

  shifted = shifted + 1

```

Files used were the examples provided in the assignment. 


file1: ACTGACTTTT


file2: TTTAGCCGAT


file3: TTTTGTCGAT


file4: TTTAGCCGATT


file5: ACTGAGCT


file6: ACTBCGACTA


Examples:


Please state the first file to be used: file1

Please state the second file to be used: file2

 Menu

 1: Display total matching pairs. 


 2: Display total contiguous pairs. 


 3: Display Both. 

Please make your selection: 1


Please enter the maximum shift: 3


['A', 'C', 'T', 'G', 'A', 'C', 'T', 'T', 'T', 'T']

['T', 'T', 'T', 'A', 'G', 'C', 'C', 'G', 'A', 'T']

No shifting provides 3 matche(s) 


['0', 'A', 'C', 'T', 'G', 'A', 'C', 'T', 'T', 'T', 'T']

['T', 'T', 'T', 'A', 'G', 'C', 'C', 'G', 'A', 'T', '0']

The first list shifted by 1 has 3 matche(s) 

['0', '0', 'A', 'C', 'T', 'G', 'A', 'C', 'T', 'T', 'T', 'T']

['T', 'T', 'T', 'A', 'G', 'C', 'C', 'G', 'A', 'T', '0', '0']

The first list shifted by 2 has 1 matche(s) 

['0', '0', '0', 'A', 'C', 'T', 'G', 'A', 'C', 'T', 'T', 'T', 'T']

['T', 'T', 'T', 'A', 'G', 'C', 'C', 'G', 'A', 'T', '0', '0', '0']

The first list shifted by 3 has 2 matche(s) 

['A', 'C', 'T', 'G', 'A', 'C', 'T', 'T', 'T', 'T', '0']

['0', 'T', 'T', 'T', 'A', 'G', 'C', 'C', 'G', 'A', 'T']

The second list shifted by 1 has 2 matche(s) 

['A', 'C', 'T', 'G', 'A', 'C', 'T', 'T', 'T', 'T', '0', '0']

['0', '0', 'T', 'T', 'T', 'A', 'G', 'C', 'C', 'G', 'A', 'T']

The second list shifted by 2 has 1 matche(s) 

['A', 'C', 'T', 'G', 'A', 'C', 'T', 'T', 'T', 'T', '0', '0', '0']

['0', '0', '0', 'T', 'T', 'T', 'A', 'G', 'C', 'C', 'G', 'A', 'T']

The second list shifted by 3 has 0 matche(s)







Please state the first file to be used: file3

Please state the second file to be used: file4

 Menu

 1: Display total matching pairs. 


 2: Display total contiguous pairs. 


 3: Display Both. 

Please make your selection: 2


Please enter the maximum shift: 5


['T', 'T', 'T', 'T', 'G', 'T', 'C', 'G', 'A', 'T', '0']

['T', 'T', 'T', 'A', 'G', 'C', 'C', 'G', 'A', 'T', 'T']

No shifting provides 4 contiguous. 

['0', 'T', 'T', 'T', 'T', 'G', 'T', 'C', 'G', 'A', 'T', '0']

['T', 'T', 'T', 'A', 'G', 'C', 'C', 'G', 'A', 'T', 'T', '0']

The first list shifted by 1 has 2 contiguous. 

['0', '0', 'T', 'T', 'T', 'T', 'G', 'T', 'C', 'G', 'A', 'T', '0']

['T', 'T', 'T', 'A', 'G', 'C', 'C', 'G', 'A', 'T', 'T', '0', '0']

The first list shifted by 2 has 1 contiguous. 

['0', '0', '0', 'T', 'T', 'T', 'T', 'G', 'T', 'C', 'G', 'A', 'T', '0']

['T', 'T', 'T', 'A', 'G', 'C', 'C', 'G', 'A', 'T', 'T', '0', '0', '0']

The first list shifted by 3 has 1 contiguous. 

['0', '0', '0', '0', 'T', 'T', 'T', 'T', 'G', 'T', 'C', 'G', 'A', 'T', '0']

['T', 'T', 'T', 'A', 'G', 'C', 'C', 'G', 'A', 'T', 'T', '0', '0', '0', '0']

The first list shifted by 4 has 1 contiguous. 

['0', '0', '0', '0', '0', 'T', 'T', 'T', 'T', 'G', 'T', 'C', 'G', 'A', 'T', '0']

['T', 'T', 'T', 'A', 'G', 'C', 'C', 'G', 'A', 'T', 'T', '0', '0', '0', '0', '0']

The first list shifted by 5 has 1 contiguous. 

['T', 'T', 'T', 'T', 'G', 'T', 'C', 'G', 'A', 'T', '0', '0']

['0', 'T', 'T', 'T', 'A', 'G', 'C', 'C', 'G', 'A', 'T', 'T']

The second list shifted by 1 has 3 contiguous. 

['T', 'T', 'T', 'T', 'G', 'T', 'C', 'G', 'A', 'T', '0', '0', '0']

['0', '0', 'T', 'T', 'T', 'A', 'G', 'C', 'C', 'G', 'A', 'T', 'T']

The second list shifted by 2 has 2 contiguous. 

['T', 'T', 'T', 'T', 'G', 'T', 'C', 'G', 'A', 'T', '0', '0', '0', '0']

['0', '0', '0', 'T', 'T', 'T', 'A', 'G', 'C', 'C', 'G', 'A', 'T', 'T']

The second list shifted by 3 has 1 contiguous. 

['T', 'T', 'T', 'T', 'G', 'T', 'C', 'G', 'A', 'T', '0', '0', '0', '0', '0']

['0', '0', '0', '0', 'T', 'T', 'T', 'A', 'G', 'C', 'C', 'G', 'A', 'T', 'T']

The second list shifted by 4 has 1 contiguous. 

['T', 'T', 'T', 'T', 'G', 'T', 'C', 'G', 'A', 'T', '0', '0', '0', '0', '0', '0']

['0', '0', '0', '0', '0', 'T', 'T', 'T', 'A', 'G', 'C', 'C', 'G', 'A', 'T', 'T']

The second list shifted by 5 has 1 contiguous.





Please state the first file to be used: file2

Please state the second file to be used: file3

 Menu

 1: Display total matching pairs. 


 2: Display total contiguous pairs. 


 3: Display Both. 

Please make your selection: 3


Please enter the maximum shift: 1


['T', 'T', 'T', 'A', 'G', 'C', 'C', 'G', 'A', 'T']

['T', 'T', 'T', 'T', 'G', 'T', 'C', 'G', 'A', 'T']

No shifting provides 8 matche(s) and 4 contiguous. 

['0', 'T', 'T', 'T', 'A', 'G', 'C', 'C', 'G', 'A', 'T']

['T', 'T', 'T', 'T', 'G', 'T', 'C', 'G', 'A', 'T', '0']

The first list shifted by 1 has 4 matche(s) and 3 contiguous. 

['T', 'T', 'T', 'A', 'G', 'C', 'C', 'G', 'A', 'T', '0']

['0', 'T', 'T', 'T', 'T', 'G', 'T', 'C', 'G', 'A', 'T']

The second list shifted by 1 has 2 matche(s) and 2 contiguous.




The challenges in this approach was mostly just debugging the coniguous function as well as making sure the lists were defined correctly. 
