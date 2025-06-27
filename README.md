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

** getattr(objec_name,'attributename' )
** setattr(objec_name,'attributename','new value')
** delattr(objec_name,'attributename')
** hasattr(objec_name,'attributename) 

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


# Use of built in class attributes : 
1) __dict__ : dictionary containing class's name space
2) __doc__ :  class documentation string
3) __name__ :  class name
4) __module__ : module name in which class is defined
5) __bases__ : list of base classes.

class Employee():
    '''this employee data '''
    def __init__(self,sal,ag):
        self.salary=sal
        self.age=ag

e1=Employee(23000,44)
e2=Employee(43000,35)

print(Employee.__doc__) # this employee data 
 
print(Employee.__dict__) #{'__module__': '__main__', '__firstlineno__': 1, '__doc__': 'this employee data ', '__init
print(Employee.__name__) # Employee 
print(Employee.__module__)  # __main__

#  isinstance() function
# syntax : isinstance(obj_name,classname)

class Demo():
    pass

d1=Demo()
d2=Demo()


class Display():
    pass

di1=Display()
di2=Display()

print(isinstance(di1,Display)) # True
print(isinstance(d2,Display))  # False
print(isinstance(di2,Demo))    # # False
print(isinstance(d2,Demo))  # True 


# instance variable and class variables.

# instance variable creation outside call function.

class Student():
    def __init__(self,nm,mar):
        self.name=nm
        self.marks=mar

std1=Student("ali",80)
std2=Student("rahul",70)

print(std1.__dict__)  # {'name': 'ali', 'marks': 80}
# creating instance variable outside
std1.age=24
print(std1.__dict__)  # {'name': 'ali', 'marks': 80, 'age': 24}
del std1.age
print(std1.__dict__)  # {'name': 'ali', 'marks': 80}

###### creating variable using instance method :


class Student():
    def __init__(self,nam,mar):
        self.name=nam
        self.marks=mar
    def display(self):
        print(f"{self.name} and {self.marks}")

    def change_data(self):  # changing variable.
        #self.name=input("enter name: ")
        #self.marks=int(input("enter marks: "))
         self.name="alok"
         self.marks=99



std1=Student("ajay",79)
std2=Student("ganesh",89)

std1.change_data()
print(std1.__dict__) # {'name': 'alok', 'marks': 99}

## Class variable and class method

class Employee():
    company_name="Qualcomm"  # class variable.
    def __init__(self,sal,ag):
        self.salary=sal
        self.age=ag

e1=Employee(20000,44)
e2=Employee(45000,46)
print(Employee.company_name) #  Qualcomm
Employee.company_name="tcs"  # modify class variable.
print(Employee.company_name)  # tcs

# class method ( to access variable.)

class Employee():
    company_name="infosys"
    def __init__(self,sal,agg):
        self.salary=sal
        self.age=agg
    @classmethod
    def get_company_name(cls):
        print(f"company name is ",cls.company_name)


e1=Employee(20000,45)
e2=Employee(40000,33)

Employee.get_company_name() #  company name is  infosys

# class method second example

class Student():
    college_name="RYMEC"
    def __init__(self,nam,mar):
        self.name=nam
        self.marks=mar
    @classmethod
    def getcollege_name(cls):
     cls.college_name="BIT" #  modifying varaible 
     print(f"college name is :{cls.college_name}")     # class method 

std1=Student("rahul",80)
std2=Student("akhil",90)
print(Student.college_name)  # to access class variable.
Student.getcollege_name()   #   class method.

# using setter method and getter method.

class Employee():
    def setname(self,nm):
        self.name=nm

    def getname(self):
        print("the name is :",self.name)

e1=Employee()
e2=Employee()
e1.setname("ajay")   # setting name ajay
e2.setname("ashok")   # setting name ashok
print(e1.__dict__)    #  {'name': 'ajay'}
print(e2.__dict__)    #  {'name': 'ashok'}
print(e1.name)       #  ajay
print(e2.name)       # ashok
e2.getname()      #  the name is : ashok
e1.getname()      # the name is : ajay

# static method  --perform operations on external data

class Bank():
    Bank_name="sbi"     #class variable
    rate_of_int=12.2    # class variable

    @staticmethod
    def simp_int(prin,n):
        si=(prin*n*Bank.rate_of_int)/100
        print("simple interest is " ,si)

prin=float(input("enter the principle amount:")) 
n=int(input("enter the number of years : "))

Bank.simp_int(prin,n)   #  external variables prin and n

####### inheritance -- deriving a new class from an existing class so that new class inherits all members (attributes +method) of existing  class is called inheritance.  ##

class Employee:
    bonus=1000
    def display(self):
        print("this is parent class")

class Manager(Employee):  # child class
    bonus1=2000
    def show(self):
        print("this is other function")
e1=Employee()
m1=Manager()
print(e1.bonus) # 1000
print(m1.bonus1) #  2000
print(m1.bonus)  # 1000
m1.show()  #  this is other function
e1.display()  # this is parent class











