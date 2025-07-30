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

# use of else and finally block in program 
# Note : else and finally blocks are optional
# Note : For one try block there will be multiple except blocks

num1=int(input("enter first number: "))
num2=int(input("enter second number :"))
try:
    div=num1/num2
    print(div)
except:
    print("something went wrong")  # it will execute if exception occur.
else:
    print("exception did'nt occur")  # it will execute if no exception
finally:
    print("always executed")  # it will execute always 

# Exception class example : ( NameError)

num1=int(input("enter the first number :"))
num2=int(input("enter the second number :"))
try:
    div=num1/num
    print("division is ",div)

except Exception as obj:  # NameError exception 
    print(obj.__class__)  # prints NameError class 
    print(obj)   #  it will exception information.

# Exception class example : ( Zero devision error )
num1=int(input("enter the first number :"))   # 10
num2=int(input("enter the second number :"))  # 0
try:
    div=num1/num2
    print("division is ",div)

except Exception as obj:
    print(obj.__class__)
    print(obj)

# Printing Exception name and Exception info by (import sys)
# 


import sys
num1=int(input("enter first number :"))
num2=int(input("enter second number :"))

try:
    div=num1/num
    print("division is :",div)
except:
    print(sys.exc_info()[0])  # prints Exception name class
    print(sys.exc_info()[1])  # prints Exception info 

# Exception handling using function method.

Example 1. 

import sys
def div(a,b):
    x=a/b
    print(x2)

try:
    div(6,2)
except:
    print(sys.exc_info()[0])
    print(sys.exc_info()[1])

Example 2. 

def div(a,b):
    x=a/b
    print(x)

try:
    div(6,0)
except Exception as obj:
    print(obj)

Example 3.

def div(a,b):
    x=a/b
    print(x)

try:
    div(6,0)
except ZeroDivisionError:
    print("can not divided by zero")

# raise an exception :

syntax :  raise exceptionName("error message")

# Normal method : 

age=int(input("enter the age "))

try:
    if age < 0:
        raise ValueError("Age cannot be negative")
    print("age is ", age)

except ValueError as obj:
    print(obj)
    
# using function  :

def set(age):

    if age < 0:
        raise ValueError("Age cannot be negative")
    print("age is ", age)

try:
    set(-5)

except ValueError as obj:
    print(obj)
    
# User defined Exception :  
# writing program for FiveDivisionError.

class FiveDivisionError(Exception):
    pass

try:
    n1=int(input("enter the first number : "))
    n2=int(input("enter the second number : "))
    if n2==5:
        raise FiveDivisionError("can not divided by five")
    x=n1/n2
    print("the division is :",x)

except (FiveDivisionError,ZeroDivisionError) as obj:
    print(obj)

# write program to to check withdraw amount :

class  insufficient_fund(Exception):
    pass
main=10000

try:
    amount=int(input("enter withdrawl amount :"))
    if amount > main:
        raise insufficient_fund("you can not withdraw amount")
    main-=amount
    print("the balance is :",main)

except insufficient_fund as obj:
    print(obj)

# calculator example :

class OperationError(Exception):
    pass
class OperatorError(Exception):
    pass

def calculator():
    operations=('+','-','*','/')
    user_input=input("enter the operation :")
    element=user_input.split()
    try:
        if len[element]!=3:
            raise OperationError("enter two operand with operator seperated by spaces")
        operator=element[1]
        if operator not in operations:
            raise OperatorError(f"{operator} is not valide,enter it form {operations}")
        num1=float(element[0])
        num2=float(element[2])
        if operator=='/' and num2==0:
            raise ZeroDivisionError("can not divided by zero")
           
        
    except Exception as e:
        print(e)
        print("Try again")
        calculator()
    else:
        if operator=='+':
            result= num1 + num2
        
        elif operator=='-':
            result= num1-num2
        
        elif operator=='*':
            result= num1 * num2
        
        elif operator=='/':
            result = num1/num2
        
        
    finally:
        return f"{num1} {operator} {num2} = {results}"
    
result=calculator()
print(result)
        
        
        
        
        


