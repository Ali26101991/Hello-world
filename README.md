
# def fun_name() in python

def my_firstfun():
    print("first function")
    
my_firstfun()

##########################################
# function to find square root
def square_root(number):
    print(number**2)
square_root(5)

###########################################

def arguments(num1,num2):
    print(num1+num2)
    print(num1-num2)
    print(num1*num2)
    print(num1/num2)

#arguments(10,2) we can use this as well.   
arguments(num1=10,num2=2)

###########################################

def list_value(*number):
    print(number[0],number[1])
    
lst=[5,4,3,2,1]
list_value(*lst)

############################################

def keyword_pas(**number):
    print("first number is : " + number['integer'] + "other number is" + number['integer2'])

keyword_pas(integer="540 ",integer2=" 444")


#####################################
# we can assign as many as keywork using below method

def addvalue(**value):
    print("first value is:"+ value['num'] + "other value is :"+ value['num1'] )

addvalue(num="333 ",num1="444")

########################################

def subNumbers(x,y):
    return(x-y)
    
a=40
b=20
res=subNumbers(a,b)
print("the sub of both number is : ",res)

#########################################

def add(x,y):
    return(x+y)
    
addition=add(4,2)
print(addition)
########################################
def my_function(x):
    return x*5
my_function(4)
print(my_function(4))
print(my_function(6))
print(my_function(8))

##########################################
#sorted() function 
def func(nm):
  return  nm.split()[1]

data=["kohli virat","tendulkar sachin","pandey hardik","ishan sharma"]
print(sorted(data,key=func))

########################################
# using lambda function 

lambda nm:nm.split()[1]
data=["kohli virat","tendulkar sachin","pandey hardik","ishan sharma"]
print(sorted(data,key=lambda nm:nm.split()[1]))


# nested function 

def outer():
    def add(num1,num2):
        return num1+num2
    return add
add= outer()
print(add(4,4))

## nested lamda function


outer=lambda:lambda num1,num2:num1+num2
add=outer()
print(add(4,6))

######  if - else
n1=10
n2=20
if n1>=n2:
    print(n1)
else:
    print(n2)
############  short hand if else  
    
x= n1 if n1>=n2 else n2

print(x)

##############  if-else using lambda

y=lambda n1,n2:n1 if n1>=n2 else n2
print(y(4,5))
    
 ############ LIST COMPREHENSION ##############
 
 # syntax 1: [ expression for variable in iterable]
nums=[3,6,8,12,14,15]

lis=[]
for num in nums:
    lis.append(num*num)
print(lis)

print([num*num for num in nums ])

# syntax 2; if condition
# [expression for variable in iterable if cond]

nums=[5,4,3,8,12,15,14]
lis=[]
for num in nums:
    if num%2==0:
     lis.append(num*num)

print(lis)

print([num*num for num in nums if num%2==0])

# syntax 3 : nested if 
#[expression for varialble in iterable if cond1 if cond2]

nums=[5,4,3,8,12,15,14]
lis=[]
for num in nums:
    if num%2==0:
        if num%3==0:
          lis.append(num*num)

print(lis)

print([num*num for num in nums if num%2==0 if num%3==0 ])
# syntax :4
#[expression if cond else expression for variable in iterable ]

nums=[5,4,3,8,12,15,14]
result=[]
for num in nums:
    if num%2==0:
        print(result.append(num*num))
    else:
        print(result.append(num*num*num))
        
print(result)
print([num*num if num%2==0 else num*num*num for num in nums])

############################################
#syntax: 5
lis=[]
for i in range(3,6):
     for j in range(5,7):
         lis.append(i*j)
print(lis)
############# using list comprehension.
print([i*j for i in range(3,6) for j in range(5,7) ])

######## IIFE Function in python
    
func=(lambda a:a+1)(int(input("enter a number ")))
print("the new value is ", func) 
    
