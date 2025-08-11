Multithreading in Python : 
Multitasking in python :  I) Process based  II) Thread based multitasking
I) Process based multitasking 
* Each task is an independent of program/process
* used at os level
II) Thread based multitasking
* Each task is an independent of thread (seperate part of program )
* used at programatic level.
# Thread :
* Thread is operating system object that executes instruction/program.
* Thread is seperate flow of execution in program
* Thread  represent  task / sub program.
# Advantages
* Improve performance of the system/application
* reduce response time of website/application.
* we can acheive threading using module # threading
# Threads are python objects of threading.Thread() class

# example : 
import threading
print(threading.current_thread().name) #MainThread
print(threading.current_thread().ident) #132391897009024
print(threading.current_thread())#<_MainThread(MainThread, started 132391897009024)>
print(threading.current_thread().is_alive())# True

# there are two ways to create threads
i) Using Thread class present in threading module.
ii) By extending Thread class.

Steps to create thread by i) method
1) import Thread class form threading module
2) Create a function containing code to be executed parralley
3) Create an object of Thread class
4) Start created thread using start() method.

# example :
# 1) import Thread class form threading module
from threading import Thread

# 2) Create a function containing code to be executed parralley
def display():
    for i in range(4):
        print("hello")
# 3) Create an object of Thread class
t1=Thread(target=display)
# 4) Start created thread using start() method.
t1.start()
##################################################
what happens when t1.start() exeucuted , interpreter call to below method
threading module:-
class Thread
   def run(self):
      display()

# by passing arguments :

# 1) import Thread class form threading module
from threading import Thread

# 2) Create a function containing code to be executed parralley
def display(n,msg): # passing arguments
    for i in range(n):
        print(msg)
# 3) Create an object of Thread class
t1=Thread(target=display,args=(4,"hello")) # passing argu
# 4) Start created thread using start() method.
t1.start()

# passing single argument :

# 1) import Thread class form threading module
from threading import Thread

# 2) Create a function containing code to be executed parralley
def display(n): # passing single arguments
    for i in range(n):
        print("hello")
# 3) Create an object of Thread class
t1=Thread(target=display,args=(6,)) # passing single arg
# 4) Start created thread using start() method.
t1.start()

# using keyword arguments :

# 1) import Thread class form threading module
from threading import Thread

# 2) Create a function containing code to be executed parralley
def display(n,msg): # passing single arguments
    for i in range(n):
        print(msg)
# 3) Create an object of Thread class
t1=Thread(target=display,kwargs={'n':4,"msg":"hello"})# passing single arg
# 4) Start created thread using start() method.
t1.start()

# working of main thread and t1 thread in below program

from threading import Thread
def display(n,msg): 
    for i in range(n):
        print(msg)
t1=Thread(target=display,kwargs={'n':4,"msg":"hello"})
t1.start()
# below code is executed by main thread and above executed by t1 thread. so we have two threads here.
for i in range(4):
    print("welcome")

# to know the current thread details :

from threading import Thread,current_thread
def display(n,msg): 
    print(current_thread()) # <Thread(Thread-1 (display), started 135932260628160)> 
    print(current_thread().name)# Thread-1 (display)
    print(current_thread().ident) # 135932260628160
    for i in range(n):
        print(msg)
t1=Thread(target=display,kwargs={'n':4,"msg":"hello"})
t1.start()
for i in range(4):
    print("welcome")
    
# accessing class method using thread

from threading import Thread  # importing module

class example:
    def display(self):  # instance method
        for i in range(4):
            print("VT1300")
e1=example()          #  create object of class example
t1=Thread(target=e1.display())  #  way to call method ( t1 thread)
            
for i in range(5):  ( here it is mainthread)
    print("welcome")

##################################################################
# accessing using class directy by @classmethod 

from threading import Thread

class example:
    @classmethod   # use of @class method
    def display(self):
        for i in range(4):
            print("VT1300")
e1=example()
t1=Thread(target=example.display()) # target using class name,you can give e1 as well.
            
for i in range(5):
    print("welcome")
########################################################
# using @staticmethod 

from threading import Thread

class example:
    @staticmethod   # using @staticmethod
    def display(n):
        for i in range(n):
            print("VT1300")
e1=example()
t1=Thread(target=example.display(4,))
            
for i in range(5):
    print("welcome")
########################################################
# ii) By extending Thread class. ( create thread )

from time import sleep
from threading import Thread

videos=["all is well","all in one","one nation"]

class myclass(Thread):
    def run(self):
        for vid in videos:
            print(f"{vid} started uploading")
            sleep(3)
            print(f"{vid} uploaded successufully ")
t1=myclass()
t1.start()

for i in range(4):
    print("checking copyrights")
    sleep(4)

#######################################################
# use constructor in class :

from time import sleep
from threading import Thread

videos=["all is well","all in one","one nation"]

class myclass(Thread):
    def __init__(self):   # adding constructor.
        print("constrcutor called")
        Thread.__init__(self)  # must call this constructor 
    def run(self):
        for vid in videos:
            print(f"{vid} started uploading")
            sleep(3)
            print(f"{vid} uploaded successufully ")
t1=myclass()
t1.start()

for i in range(4):
    print("checking copyrights")
    sleep(4)

#############################################################

from time import sleep
from threading import Thread

videos=["all is well","all in one","one nation"]

class myclass(Thread):
    def __init__(self,val):
        self.kid=val    # adding instance variable to check suitable for kids
        print("constrcutor called")
        Thread.__init__(self)
    def run(self):
        if self.kid:
            print("video is suitable")
        for vid in videos:
            print(f"{vid} started uploading")
            sleep(3)
            print(f"{vid} uploaded successufully ")
t1=myclass(True)  # if True it prints message ,if False it will not print
t1.start() 

for i in range(4):
    print("checking copyrights")
    sleep(4)
###############################################################

from time import sleep
from threading import Thread

videos=["all is well","all in one","one nation"]

class myclass(Thread):
    def __init__(self,val):
        self.kid=val
        print("constrcutor called")
        Thread.__init__(self)
    def compressor(self):   # we can add method
        print("video compressed")
    def run(self):
        self.compressor()  # call to method here
        if self.kid:
            print("video is suitable")
        for vid in videos:
            print(f"{vid} started uploading")
            sleep(3)
            print(f"{vid} uploaded successufully ")
t1=myclass(True)
t1.start()

for i in range(4):
    print("checking copyrights")
    sleep(4)

##################################################
Thread name :  example :  Thread-1 ,Thread-2
Name of thread is stored in 'name' attribute of thread object.
# printing name of thread.
from threading import Thread

def display():
    for i in range(4):
        print("hello")
def show():
    for i in range(5):
        print("world")
        
t1=Thread(target=display)
t2=Thread(target=show)
t1.start()
t2.start()
print(t1.name) # prints thread name
print(t2.name) # prints thread name

########## changing name of the thread :

from threading import Thread,current_thread

def display():
    for i in range(4):
        print("hello")
def show():
    for i in range(5):
        print("world")
        
t1=Thread(target=display)
t2=Thread(target=show)
t1.start()
t2.start()
t1.name='newname' # we can change name of thread
print(t1.name)   
t2.name='uniquename' # we can change name of thread
print(t2.name) 
print(current_thread().name)
current_thread().name="malik" # we can change name of thread
print(current_thread().name)

# Thread Identifier :
i) Thread Identifier
ii) Native Identifier

i) Thread Identifier :-
* Each thread has unique identifier(id) with a python process
* assigned by the python interpreter
* read only positive intiger and unique in process
* assigned after starting the thread
* This identifier is stored in instance varialble 'ident'

ii) Native Identifier :-
* Each thread has unique identifier assigned by operating system.
* property name: native_id (assigned after thread has started )
* Generally ident and native_id are same.

# PID
* Identifier for your process (program)
* os module  :- getpid()

  # printing Thread identifier , native identifier and PID in below progarm

  from threading import Thread
import os

def display():
    for i in range(4):
        print("hello")
        
def show():
    for i in range(5):
        print("bye")
        
t1=Thread(target=display)
t2=Thread(target=show)
t1.start()
t2.start()
print(t1.ident) # prints identifier
#print(t2.ident) # print identifier
print(t1.native_id) # prints native id
#print(t2.native_id)
print(os.getpid()) # prints PID number

# Built in function in Multithreading
* is_alive() :- checks thread running or not
* main_thread() :- it returns the main thread details
* active_count() :- Number of running thread
* enumerate() :-  list of all running thread.
* get_native_id() :- gives native id of thread.

# Example :

from threading import Thread,active_count,enumerate,get_native_id,main_thread

def display():
    print(enumerate()) # give the list of running thread (t1 and main thread )
    print(main_thread()) # prints main thread.
    for i in range(2):
        print("hello")

def show():
    for i in range(2):
        print("world")
        
t1=Thread(target=display)
print(t1.is_alive()) # before -- True
t1.start()
print(active_count()) # t1 and mainthread
print(t1.is_alive())  # After -- Start
print(get_native_id()) # prints native id

#  join()  function

if thread wants to wait for other thread then we need to go for join() method

# example :

from threading import Thread

def display():
    for i in range(4):
        print('hello')
        
def show():
    for i in range(3):
        print('VT-1300')
        
t1=Thread(target=display)
t2=Thread(target=show)
t1.start()
t1.join() # t1 will execute completely then t2 and main thread.
t2.start()
t2.join() # t2 will execute completely next main thread will execute

for i in range(4):
    print("kiwi")

# efficiency of threading system

from threading import Thread
import time

def square(num):
    print("finding square.....")
    time.sleep(1)
    print(f"the square of {num} is ", num**2)
    
def cube(num):
    print("finding cube.......")
    time.sleep(1)
    print(f"the cub of {num} is :",num**3)
begin=time.time()  #  starting of system to till now , return seconds
t1=Thread(target=square,args=(4,))
t2=Thread(target=cube,args=(3,))
t1.start()
t2.start()
t1.join()
t2.join()
print("total time taken :",time.time()-begin) # prints time taken to execute above threads ( 1 sec)

# without threading method , using only function take more time apporx = 2 sec

import time

def square(num):
    print("finding square.....")
    time.sleep(1)
    print(f"the square of {num} is ", num**2)
    
def cube(num):
    print("finding cube.......")
    time.sleep(1)
    print(f"the cub of {num} is :",num**3)
begin=time.time()
square(4)
cube(3)
print("total time taken :",time.time()-begin)  # 2 sec

# Race condition :-  A bug in cuncurrency program.

Example 01 :
var=value
t1(adder thread) : add the value
t2(subtractor thread): subtract the value
Above both threads are exeucuted simultaneously , we expect some inprecident output.

Example 02:
In below example available_seats are accessed by both the thread simultaneiously so output is not proper.

# example 02 :
# Bus ticketing system
from threading import *
class Bus:
    def __init__(self,name,available_seats):
        self.available_seats=available_seats
        
    def reserv(self,need_seat):
        print("available seats are :",self.available_seats)
        if need_seat<=self.available_seats:
            nm=current_thread().name
            #code
            print(f"{need_seat} are allocated to {nm}")
            self.available_seats-=need_seat
        else:
            print("seats are not available")
        
b1=Bus("orange travel",2)
t1=Thread(target=b1.reserv,args=(1,),name="ajay")
t2=Thread(target=b1.reserv,args=(1,),name="ashok")
t1.start()
t2.start()

# what is race condition ?
It is a bug generated when we do multiprocessing. It occures because of two or more thread tried to update the same varialble
and results into unreliable output.

concurrent accesses to shared resources can lead to race condition.

* Thread syncronization technique ( to fix race condition )

  a common approach to protect critical section of the code ( prevent concurrent access )

* following three thread synconization techniques
  1) Using Locks
  2) Using R-Lock
  3) Using Semaphores















