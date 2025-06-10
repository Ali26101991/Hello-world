age=20

#short hand if statement
if age>=18:
    print("yes person is eligible for vote")

age=5
if age<=5:
    print("No ticket unger age 5")
else:
    print("Need to take ticket for above 5 ")

# short hand if else    
marks=45
res="pass" if marks>=40 else "fail"
print(res)

#elif statements
age=20

if age<=12:
    print("child")
elif age<=19:
    print("teenage")
elif age<=35:
    print("young adult")
else:
    print("Adult")
 
###########################################    
age=61
is_member=False

if age>=60:
    if is_member:
        print("Avail 30% discount")
    else:
        print("Avail 20% discount")
else:
    print("No discount to avail")
    
###################################   
age=18

s="adult" if age>=20 else "minor "
print(s)



# write program to find even or odd

a= int(input(" enter a number"))

if a % 2 == 0:
    print("numbe is even")
else:
    print("number is odd")

# write program to find positive and negative intigers.
  
n=int(input("Enter a number"))

if n>0:
    print("number is positive")
elif n<0:
    print("number is negative")
else:
    print("number is zero")
    
# Write program to print positive odd , positve even, negative odd , negative even

a=int(input("enter number"))

if a>0:
    print("positive",end=" ")
    if a%2==0:
        print("even")
    else:
        print("odd")
elif a<0:
    print("Negative",end=" ")
    if a%2==0:
        print("even")
    else:
        print("odd")
else:
    print("zero")
    
#############################################

a=int(input("enter first number a:"))
b=int(input("enter second number b:"))

if a > b :
    print("a is greater thn b")
elif a < b :
    print("b is greate thn a")
else:
    print("Both a and b are same")
    
#########################################3
# match case examples

status=400
match status:
    case 400:
        print("Bad request")
    case 404:
        print("not found")
    case _:
        print("something went wrong")
##########################################        
point=(7,2)

match point:
    case (0,0):
        print("origin")
    case (x,0):
        print(f"X={x}")
    case (0,y):
        print(f"Y={y}")
    case (x,y):
        print(f"X={x},Y={y}")
        
#########################################        
point=(4,4)
  
match point:
    case (x,y) if x==y:
        print(f"Y=X at {x}")
    case (x,y):
        print("not on the diagnol")


