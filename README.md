# Usage of if, elif  and else 

m=10
if m>20:
 print("m is less than 20")
elif m<6:
    print("m is greater than 6")
elif m==11:
    print("m is equal to 10")
else:
    print(" No creteria met")

##  Program to guess random number between two ranges

import random

low=int(input("Enter lower number:"))
high=int(input("Enter higher number:"))

rnum = random.randint(low, high)


attempt=0
chance=7
while attempt<7:
  attempt+=1
  guess=int(input("enter your guess:"))
  
  if guess==rnum:
       print(f"Great found correct number is {rnum} and took {attempt}")
       break
   
  elif attempt >= chance and guess !=rnum:
       print("Better luck next time")
  
  elif guess<rnum:
       print("Please enter bit high number")
   
  elif guess > rnum:
       print("please enter bit low number")

# use of random.choice(list)  

import random

my_list=["apple","Banana","kiwi","orange","Mosambi"]
random_name=random.choice(my_list)
print(random_name)


