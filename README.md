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

# two types of decorators :  
* Function Decorator
* Class decorator





