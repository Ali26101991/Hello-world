# Python Boolean

a=True
b=False
print(type(a))
print(type(b))

# Python bool() function

x= None
print(bool(x))

y=()
print(bool(y))

z={}
print(bool(z))

x=0.0
print(bool(x))

x="Bangalore"
print(bool(x))

# Any number with a value of zero (0, 0.0) is considered False while any non-zero number (positive or negative) is considered True.

var1=0
print(bool(var1))
var2=1
print(bool(var2))
var3=-9.3
print(bool(var3))

# Boolean operators

# Boolean or operator.

a=5
b=3
c=8
if a>b or b<c:
    print("true")
# Boolen and operator.
a=0
b=2
c=4
if a>b and b<c:
    print(True)
else:
    print(False)
    
if a and b and c:
    print("True")
else:
    print("False")

a=0
if not a:
    print("false")

# Python Boolean == (equivalent) and != (not equivalent) Operator
a=4
b=7

if a == 0:
    print("True")
if a == b:
    print("True")
if a == 5:
    print("False")
if b == 7:
    print("True")
    
if b != a:
    print("True")

# python " is " operator 
x=10
y=10.0
if x is y:         # output : False
    print("True")
else:
    print("False")
m=20
n=20
if m is n:         # output : True
    print("True")
else:
    print("False")
    
# Python "in" operator

a=[1,2,4,6,7]
if 8 in a:      # output: False
    print("True")
else:
    print("False")
    
    

