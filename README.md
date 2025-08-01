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
























