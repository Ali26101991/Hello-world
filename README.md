# Polymorphism using reversed() fucntion :

list1=["ajay","ali","mahe"]   # 
str="gulbarga"

for i in reversed(str):
    print(i)     # it will reverse words in list

for i in reversed(list1):
    print(i)        # it will reverse character in string.

# Polymorphism with inheritance :

class Veh:
    def __init__(self,name,color,price):
        self.name=name
        self.color=color
        self.price=price

    def get_details(self):
        print("name is ",self.name)
        print("color is ",self.color)
        print("price is ",self.price)

    def max_speed(self):
        print("the max speed is 100")

    def gear(self):
        print("the number of gear are 6 ")

class Car(Veh):
    def max_speed(self):
        print("the max speed is 140")

    def gear(self):
        print("the number of gears are 7")


v1=Veh("ford","while",100000)  
v1.get_details() 
c1=Car("toyota","red",200000) 
c1.get_details()
v1.max_speed()  # 
c1.max_speed()

### overiding built in function ( __str__ )

class Cart:
    pass

c1=Cart()
print(c1)  #  <__main__.Cart object at 0x000001704CBB92B0>

###  below is example of overding 

class Cart:
    def __str__(self):
        return "hello world"

c1=Cart()
print(c1)   # hello world

# overiding len() function 

class Cart:
    def __init__(self,bask1,bask2,bask3):
        self.clothes=bask1
        self.electronics=bask2
        self.others=bask3
    
c1=Cart(["pant","shirt","hoodi"],["tv","mob"],["chair"])
print(len(c1))  # error

##  after defining len() function.
class Cart:
    def __init__(self,bask1,bask2,bask3):
        self.clothes=bask1
        self.electronics=bask2
        self.others=bask3
    def __len__(self):
        return len(self.clothes)+len(self.electronics)+len(self.others)

c1=Cart(["pant","shirt","hoodi"],["tv","mob"],["chair"])
print(len(c1))    # 6 


#  Polymorphism in Functions and Objects

class BMW:
    def max_speed(self):
        print("speed is 300")
    def fuel_type(self):
        print("this diesel")

class VW:
    def max_speed(self):
        print("speed is 200")

    def fuel_type(self):
        print("this petrol")
def Car(obj):
    obj.max_speed()
    obj.fuel_type()

B1=BMW()
V1=VW()  
Car(B1)  # speed is 300  , this diesel
Car(V1)  # speed is 200 , this petrol


# Using int data types
num1=20
num2=30
print(num1+num2)  # adding using variables
print(num1.__add__(num2))  # first method
print(int.__add__(num1,num2))  # second method

# using string data type
str1="maheboob"
str2="ali"
print(str1+str2) # normal method
print(str1.__add__(str2))  # we can write this as well
print(str.__add__(str1,str2)) # we can write this as wel.
print(dir(str))

print("hellow"+20)  # throw type error

# adding functions to user defined classes

class Book():
    def __init__(self,title,pages):
        self.title=title
        self.pages=pages
    def __add__(b1,b2):  #  adding add function
        return b1.pages+b2.pages

b1=Book("the lucky man",300)
b2=Book("the power",200)

print(b1+b2)  ##  Book.__add__(b1,b2)
print(Book.__add__(b1,b2))
print(b1)
print(b1.__dict__)


############ adding b3 objecct 

class Book:
    def __init__(self,title,pages):
        self.title=title
        self.pages=pages

    def __add__(self,other):
        total=self.pages+other.pages
        return Book("all books",total)

    def __str__(self):
        return str(self.pages)

b1=Book("hello world",300)
b2=Book("magic number",200)
b3=Book("many fires",450)
print("the total pages are :",b1+b2+b3)

# operator over writting.

class Hotel:
    def __init__(self,name,fare):
        self.name=name
        self.fare=fare

    def __gt__(self,other):   # overiding value
        return self.fare>other.fare

h1=Hotel("taj",20000)
h2=Hotel("pvr",10000)

print(h1>h2)  # Hotel.__gt__(h1,h2)
print(Hotel.__gt__(h1,h2))

################################
# Method overloading : 

class addition:
    def add(self,num1,num2):  # shows type error
        print("addition of two number is ",num+num2)

    def add(self,num1,num2,num3): # last defined method will execute always
        print("addition of three num is ",num1+num2+num3)

a=addition()
a.add(4,6,4)   # addition of three num is  14

#  Method overloading using None , it will execute given arguments without error.

class Calci:
    def add(self,num1=None,num2=None,num3=None):
      if num1!=None and num2!=None and num3!=None:
          print("addition is : ",num1+num2+num3)
      elif num1!=None and num2!=None:
          print("addition is :",num1+num2)
      else:
          print("numbers are incorrect")
c1=Calci()
c1.add(4,5)  # addition is : 9
c1.add(4,5,6)  # addition is :  15

# in this example last defined method will execute 
class Area:
    def Size(self,l):
        print("the area of square is",l*l)

    def Size(self,l,b):
        print("the area of ractangle is ",l*b)

a1=Area()
a1.Size(2)  # Error
a1.Size(2,4)  # the area of ractangle is  8

# to avoid eror 

class Area:
    def Size(self,l=0,b=0):
        if l>0 and b>0:
         print("the area of ractangle is",l*b)
        elif l>0 and b==0:
         print("the area of square is",l*l)



a1=Area()
a1.Size(4,3)

# Nested class :

class Student:
    def __init__(self,name,roll,dd,mm,yy):
        self.name=name
        self.roll=roll
        self.dob=self.DOB(dd,mm,yy)

    def display(self):
        print(f"name is {self.name} and roll is {self.roll}")
        self.dob.display()

    class DOB:
        def __init__(self,dd,mm,yy):
            self.date=dd
            self.month=mm
            self.year=yy
        def display(self):
            print(f"the data of birth is {self.date}/{self.month}/{self.year}")


s1=Student("ajay",110,26,10,1991)
s1.display()










