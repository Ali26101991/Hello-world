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





