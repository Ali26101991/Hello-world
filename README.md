# recursion : when function calls itself then that function is called recursive function and that process is called recursion
# by default recursion will run upto 1000 times
# we can get the recursion limit and we can set the recursion limit.
'''
# example
import sys
sys.setrecursionlimit(200)
i=0
def demo():
    global i # to use global variable
    i=i+1   #  it count number of prints
    print("hello",i)
    demo() # recursion function, inside def.
demo() # calling outside def  

############ to check recursion limit ##########

import sys   # import module 
print(sys.getrecursionlimit()) # function.

############ to set recursion limit ###########
import sys   # import module 
print(sys.setrecursionlimit(200))
'''

########################################
# direct recursion
#write program to print n to 1 sequence
# 10--- 10,9,8,7,6,5,4,3,2,1
def natural(n):
    print(n)
    if n==1:
        return
     
    return natural(n-1)
    
natural(13)

#indirect recursion --- a function calls another function which then calls the first function again.

def num(n):
    if n<=0:
        return
    print(n,end=" ")
    num1(n-1)

def num1(n):
    print(n,end=" ")
    num(n-1)
    
num1(10)







    
    
    
    
    
    
    
    
    
    
