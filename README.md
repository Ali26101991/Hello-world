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

