Excepthook in Python :
Once Exception occur below steps executed
* the interpreter calls sys.Excepthook() with three arguments
* i) exception class
* ii) exception instance/value
* iii) a traceback object

this function prints out a given traceback and exception to sys.stderr
In an interactive session this happens just before control is returned to the prompt.

syntax : def excepthook(exc_type,exc_value,exc_traceback):
          prints arguments here.
use of excepthook :
* we can customize output by overidding this function
* sys.excepthook handles uncaught exceptions.

Example 1:

import sys
def format_traceback(exc_type,exc_value,exc_traceback):
    print("something went wrong")
sys.excepthook=format_traceback

def Display():
    print(1+"ali")
Display()

## additional code :

import sys
def format_traceback(exc_type,exc_value,exc_traceback):
    print("something went wrong")
    print(exc_type)
    print(exc_value)
    print(exc_traceback)
sys.excepthook=format_traceback

def Display():
    print(1+"ali")
Display()



