# user defined Class 
class Email():
    pass

e1=Email()
e2=Email()
print(type(e1))  # <class '__main__.Email'>

# exaple of class with non parameterized constructor.

class Employee():
    def __init__(self):   # __init__ is non parameterized constructor.
        self.salary=22000
        self.age=21

e1=Employee()   # object1
e2=Employee()   # object2
print(e1.__dict__)  # {'salary': 22000, 'age': 21}

# example of class with Parameterized constructor.
class Employee():
    def __init__(self,sal,ag): # __init__ is parameterized constructor
        self.salary=sal
        self.age=ag

e1=Employee(23000,31)
e2=Employee(44000,44)
print(e1.__dict__)  # {'salary': 23000, 'age': 31}
print(e2.__dict__)  # {'salary': 44000, 'age': 44}


# Below program depicts how to access attributes (varaible) and method

# access attribute :  objectname.variable name
# access method :  objectname.methodname()

#Example 1 : 
class Employee():
    def __init__(self,sal,ag):
        self.salary=sal    #  attributes/varaible
        self.age=ag        #  attributes/varaible

    def display(self):     # method
        print(f"salary is {self.salary} and age is {self.age}")

e1=Employee(24000,45)  # object1
e2=Employee(35000,65)  # object2

print(e1.salary) #24000
print(e1.age)  # 45
print(e2.salary) # 35000
print(e2.age) # 65
e1.display()  #  salary is 24000 and age is 45

#Example 2:

# write program to print student name and marks

class Student():
    def __init__(self,ma,nam):
        self.marks=ma
        self.name=nam
    def display(self):
        print(f"name is {self.name} and marks is {self.marks}")

std1=Student(60,"atul")
std2=Student(70,"ajay")
print(std1.marks)   # access attributes
print(std1.name)
std1.display()       # access methods
std2.display()

Example 3:

# write a program to print college name, rank and city .

class College():
    def __init__(self,nam,ran,cit):
        self.name=nam
        self.rank=ran
        self.city=cit

    def display(self):
        print(f"collge name is {self.name},rank is {self.rank} and city is {self.city}")
clg1=College("rym",1,"hyd")
clg2=College("BIM",2,"Ban")

print(clg1.name)
clg1.display()
clg2.display()

# To use built in class functions.

getattr(objec_name,'attributename' )
setattr(objec_name,'attributename','new value')
delattr(objec_name,'attributename')
hasattr(objec_name,'attributename) 

Example 4: 

class Employee():
    def __init__(self,sal,ag):
        self.salary=sal
        self.age=ag

e1=Employee(23000,44)
e2=Employee(43000,35)
print(e1.__dict__) # {'salary': 23000, 'age': 44}
print(e1.salary) # 23000
print(e1.age) #  44
print(getattr(e1,"salary")) # 23000
print(getattr(e1,"age")) # 44
setattr(e1,'salary','10000') # setting salary to 10000
print(getattr(e1,"salary")) #  10000
delattr(e1,"salary") # deleting salary attributte
print(e1.__dict__)  #  {'age': 44} 
print(hasattr(e1,'age')) # True -- check presence of age attr
print(hasattr(e1,'nam')) # False -- check presence of nam attr




