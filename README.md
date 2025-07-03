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


















