Exception Handling in python

* What Exception ?
  An Exception is an event which occurs during the execution of the program that distrupts normal flow of program.
  It is situation which python can'nt cope with it.

* Why it is dangerous?
  Lead to sudden termination of program.
  Can block the application.
  Data loss problem can occur.
  Corrupt data files

* Error can not be handled whereas Exception can handled by exception handling syntax.
* 4 blocks to handle exception.
   1. try block
   2. except block
   3. else block
   4. finally block
 
Syntax :
      try:
            # code containig exceptions (suspecious code )
      except [ Exception Name ]  
            # code to handle exceptions (if occured )
      else: 
            # code execute if no exceptions occured

      finally: 
            # always executed 

# example without exception :

num1=int(input("enter first number :"))
num2=int(input("enter second number :"))
div=num1/num2
print(div)
print("rest of code")
      
# example with exception :

num1=int(input("enter first number :"))
num2=int(input("enter second number :"))
try:
    div=num1/num2
    print(div)
except ZeroDivisionError:
    print("devided by zero not possible")

print("rest of code")

# handling multiple exceptions:

num1=int(input("enter first number :"))
num2=int(input("enter second number"))

try:
    div=num1/num2
    print(di)
except ZeroDivisionError:    
    print("can not devided by zero")
except NameError:
    print("varialbe name is wrong")

# to print exact exception from output window 

num1=int(input("enter first number :"))
num2=int(input("enter second number :"))

try:
    div=num1/num2
    print(di)
except (ZeroDivisionError,NameError) as obj:
    print(obj)

# common print message for all exception 

num1=int(input("enter first number: "))
num2=int(input("enter second number :"))
try:
    div=num1/num2  # if num2 0 , ZeroDivisionError
    print(di)  # NameError
except:
    print("something went wrong")




