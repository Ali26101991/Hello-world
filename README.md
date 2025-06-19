
# Function as an argument
def getname():
    nm= (input("enter first name: "))
    last_nm=(input("enter last name :"))
    return nm +" "+ last_nm

def display(func):
    print(func())

display(getname)

#####################################

def display():
    print("hello")
    def printer():
        print("welcome")
###########################################
#return function from function.
def display():
    print("hello")
    def printer():
        print("welcome")
    return printer
val=display()
val()
    
###########################################

def add(x,y):
    return x+y

def display(func):
    print(func(4,6))
    
display(add) ### this is higher order function, it takes other function as parameter.

########Build in higher order function.

# filter()
# map()
# reduce()

#syntax:  filter_object=filter(function_name, iterable) 

# To filter even numbers from list by using filter() funtion.

# Method-- 1
data=[22,23,44,57,88,87,65]
def even(num):
    if num%2==0:
        return True
    else:
        return False
filtered_object=filter(even, data)
print(filtered_object)
print(type(filtered_object))
print(list(filtered_object))
############################################
# method -- 2

data=[22,23,44,57,88,87,65]
def even(num):
    if num%2==0:
        return True
        
filter_obeject=filter(even, data)
print(list(filter_obeject))
########################################
#method-- 3

data=[22,23,44,57,88,87,65]
def even(num):
    return num%2==0
filter_obeject=filter(even, data)
print(list(filter_obeject))
print(list(filter_obeject)) # only once we can


# method -- 4 using for loop

data=[22,23,44,57,88,87,65]
def even(num):
    return num%2==0
filter_obeject=filter(even, data)
for ele in filter_obeject:
    print(ele,end=" ")
data=[22,23,44,57,88,87,65]
filter_obeject=filter(lambda num:num%2==0, data)
print(list(filter_obeject))
###############################
#short program using lambda fucntion

print(list(filter(lambda num:num%2==0, [22,23,44,57,88,87,65])))

# Write progrm to find vowels in string using filter function 

str1="alliswellalliswell"
vowels_list=['a','e','i','o','u']
def vowels(ch):
    if ch in vowels_list:
        return True

filter_objec=filter(vowels,str1)
print(filter_objec)
print(list(filter_objec))

##################################
# above program using lambda function.

print(list(filter(lambda ch:ch in ['a','e','i','o','u'],"alliswellalliswell")))


# Write program to to find topper list in below dictionary 


dic={"ramesh":98,"ravi":91,"kamlesh":78,"rahul":80}
def topper(students):
    return  dic[students]>=90
    
topper_list=filter(topper,dic)
print(list(topper_list))  

#############################################
#using lambda function

dic={"ramesh":98,"ravi":91,"kamlesh":78,"rahul":80}
topper_list=filter(lambda students:dic[students]>=90,{"ramesh":98,"ravi":91,"kamlesh":78,"rahul":80})
print(list(topper_list))

#Using map() function
#write program to map names with length of string.

names=['ashok','rama','rahul','mayur']
def find_len(name):
    return len(name),name

map_obj=map(find_len,names)
for ele in map_obj:
    print(ele)

#################################
#using lambda function

print(list(map(lambda name:len(name),['ashok','rama','rahul','mayur'])))
#############################################

# program to find square of number in list using map() function

list1=[3,5,6,8,2,4]
def sqr(n):
    return n**2
map_obj=map(sqr,list1)
print(list(map_obj))
#######################################
#  above program using lambda function
lambda n:n**2
map_obj=map(lambda n:n**2,[3,5,6,8,2,4])
print(map_obj)
print(list(map_obj))
#######################################
print(list(map(lambda n:n**2,[3,5,6,8,2,4])))
############################################

# to find square of even number and cube of odd number. 

list1=[3,5,6,8,2,4]
def sqr(n):
    if n%2==0:
        return n**2
    else:
        return n**3
    
map_obj=map(sqr,list1)
print(list(map_obj))


# using single iterabe 'marks'

marks=[60,30,40,50,80]
'''
bonus=[1,2,4,5,6]
bonus=[3,5,6]
'''
def logic(arg1):
    return arg1+1

map_obj=map(logic,marks)
for i in map_obj:
    print(i)

##########################################
# using multiple iterable 'marks' and 'bonus'

marks=[60,30,40,50,80]
bonus=[1,2,4,5,6]
def logic(arg1,arg2):
    return arg1+arg2
map_obj=map(logic,marks,bonus)
for i in map_obj:
    print(i)
    
###############################################
# using 3 iterables 'marks', 'bonus' and 'bonus1

marks=[60,30,40,50,80]
bonus=[1,2,4,5,6]
bonus1=[3,5,8]
def logic(arg1,arg2,arg3):
    return arg1+arg2+arg3
map_obj=map(logic,marks,bonus,bonus1)
for i in map_obj:
    print(i)


# filter() example

laptops={'hp':45000,'lenovo':55000,'asus':80000,'dell':40000}
budget=float(input("enter your budget:"))

def fir_fun(ele):
    if laptops[ele]<=budget:
        return True
    else:
        return False

fil_obj=filter(fir_fun,laptops)
print(list(fil_obj))


############ reduce() function ################


# writing program with reduce() function, it will ( below it will add two numbers and then result will be added to next number.

import functools

list1=[4,5,6,7,3,5]
def func(a,b):
    return a+b

redu_obj=functools.reduce(func,list1)
print(redu_obj)


################ using lambda function

print(functools.reduce(lambda a,b:a+b,[4,5,6,7,3,5]))   

###################### to find max number in list using reduce() function.
import functools
list1=[3,6,8,3,5,7]
def max1(a,b):
    if a>b:
        return a
    else:
        return b
    return
val=functools.reduce(max1,list1)
print(val)

