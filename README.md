# user defined Class 
class Email():
    pass

e1=Email()
e2=Email()
print(type(e1))  # <class '__main__.Email'>

# exaple of class with constructor.
class Employee():
    def __init__(self):
        self.salary=22000
        self.age=21

e1=Employee()   # object1
e2=Employee()   # object2
print(e1.__dict__)  # {'salary': 22000, 'age': 21}
