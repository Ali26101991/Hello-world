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

