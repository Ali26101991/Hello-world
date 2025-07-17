Python destructor : ( __del__)

a special method which destroys objects and releases resources tied to object

destructor is called automatically when object is destroyed.

* Purpose of destructor :  releasing objects tied to destroyed object.
 
# Below are the conditions when destructor is called  :

* Reference counting reaches to zero.
* When varialble goes out of scope.

# object creation and deletion in python. 

lets take example : emp=Employee("jay",50000)  -- > arguments passed here for constructor to intialize varaiables. 

step1: object is created using __new__() method 
step2: object is initialized using __init__() method

# del emp  : when it called  destructor invoked using __del__() mehthod

# working of destructor in python 
emp=Employee("jay",50000)
temp=emp
if you delete emp object ( del emp ) # __del__() method will not be invoked as we still have one reference.
when you call # del temp :   object is ready for garbage collection , call the destructor.

######### sample program #######

class employee:
    def __init__(self,nm,sal):
        self.name=nm
        self.salary=sal

    def display(self):
        print(f"name is {self.name} and salary is {self.salary}")

    def __del__(self):
        print("the destructor is called")

e1=employee("ajay",40)
e1.display()
del e1  #  destructor is called before deleting varialble.

###  creating multiple objects of Movie class : ( storing objs in list )

class Movie(object):
    def __init__(self,title,min,hero):
        self.title=title
        self.runtime=min
        self.hero=hero

    def printer(self):
        print(f"title is : {self.title}\nruntime is {self.runtime}\nand hero is :{self.hero}")
list_movies=[]
while True:
        title=input("enter the movie titlel : ")
        min=input("enter the movie run time :")
        hero=input("enter the hero name :")
        obj=Movie(title,min,hero)
        list_movies.append(obj)
        print("movie added into list")
        ans=input("Do you want to add other movie name(y/n)")
        if ans!="y":
            break
print("all movies information")
for obj in list_movies:
    obj.printer()

# circular referencing 

import time

class Employee:
    def __init__(self,obj2):
        self.obj2=obj2
    def __del__(self):
        print("employee class destructor called")

class Account:
    def __init__(self,num):
        self.account_num=num
        self.obj1=Employee(self)
    def __del__(self):
        print("account class destructor called")

ac=Account(1234)
del ac
time.sleep(5)

* callable() is a built in function :**
* syntax :  callable ( python object )
* It returns boolean value
* if object is callable it return true
* if object is not callable it return False

# what are callable object in python ?
1) Objects which can be called whenver required
2) objects having __call__() method in their class

Note : Classes and Function are callable objects in python. 

x=100
print(callable(x)) # False
###########################################
def add(a,b):
    return a+b

add(4,6)
print(callable(add)) # True

# Types of Decorators
Function decorator.
Class decorator.


class Decorator(object):
    def __init__(self,func):
        self.fucntion=func
    def __call__(self,a,b):
        result=self.fucntion(a,b)
        return result**2

@Decorator
def add(a,b):
    return a+b

#add=Decorator(add)
print(add(4,5))   # 81


# other example of class decorator

class Decorator:
    def __init__(self,func):
        self.function=func

    def __call__(self,*args):
        try:

            if any([isinstance(i,str) for i in args]):
                raise TypeError("Cannot pass string as argument")
            else:
                return self.function(*args)
        except Exception as obj:
            return obj



@Decorator
def add(*args):
    sum1=0
    for num in args:
        sum1=sum1+num
    return sum1

print(add(10,20,30))
print(add(10,"20",30))
#add=Decorator(add)

#   @property decorator 

# @property decorator is built in decorator

# it will treat methods as attribute
# example  instead of e.mail() we can call it e.mail

class Employee:
    def __init__(self,first,last):
        self.firstname=first
        self.lastname=last
        #self.mail=first+last+"@gmail.com"

    @property
    def mail(self):
        return f'{self.firstname}{self.lastname}@gmail.com'

    @property
    def fullname(self):
        return f'{self.firstname} {self.lastname}'

e=Employee("Rahul","Khanna")
e1=Employee("salman","khan")
e2=Employee("Manoj","parge")

e.firstname="anil"
print(e.firstname)
print(e.lastname)
print(e.mail)    # # we can skip e.mail()
print(e.fullname)  # we can skip e.fullname()
print("********************")
print(e1.firstname)
print(e1.lastname)
print(e1.mail)
print(e1.fullname) # we can skip e1.fullname()
print("********************")

# what is abstraction ?
The process by which data and functions are defined in such way that only essential details can be seen and unneccessary implimentations are hidden is called data abstraction.  

Hiding complex implementations details and showing only signetures to users.








