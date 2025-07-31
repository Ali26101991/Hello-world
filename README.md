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


























