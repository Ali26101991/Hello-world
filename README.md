
# three types of numbers in python , int, float and complex 
a=4
b=3.8
c=5j
print(type(a))  #integer
print(type(b))  # float
print(type(c))  # complex
x=10
y=5
print(x+y)
print(x-y)
print(x*y)
print(x/y)
print(x**y)
print(x%y)
print(x//y)
print(abs(-23)) #absolute value
print(round(4.2344,2)) # round off to decimal 2

#float
x=3+4j
print(x)
print(type(x))

import random

ran=random.randint(1,50)# generating random int between 1 to 50
print(ran)  

ran1=random.uniform(1.0,10.0) #generating random floating point num
print(ran1)

mylist=["apple","Banana","orange"]
name=random.choice(mylist) # random choice from given list
print(name)
# nan stands for not a number
import math
n=math.nan
print(n)

x=float('inf')
y=float('-inf')
print(x)
print(y)



