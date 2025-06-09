# Set is unordered , unindexed and mutable 

set1={ 1,2,3,4,5 }
print(set1)
# use of set() function
set1=set()
print(set1)
set2=set("maheboobali") # create set with no duplic 

print(set2) 
            #output : {'i', 'o', 'm', 'h', 'l', 'a', 'e', 'b'}
set3=set(["hello","world","hello"])# Using list ,no duplicat in output. 
print(set3)  # Output : {'hello', 'world'}

set4=set(("hello","every","one")) #using tuple
print(set4) #output {'hello', 'every', 'one'}

dic={101:"apple",102:"banana",103:"orange"}
print(set(dic)) #output : {101, 102, 103}

set5={1,5,3,6,7,9}
#print(set5[2]) # give typeerror. unindexed

set5.add(8)  # add() to add element in set
print(set5) # output{1, 3, 5, 6, 7, 8, 9}

set5.update([2,0]) # add using update() function
print(set5)

set6={"welcom","to","python"}
for i in set6:
    print(i,end=" ") #welcom to python (wil change)
    
print("to" in set6)  # output : True.

set7={5,4,3,2,1,0}
set7.remove(5) # remove()
print(set7)

set8={2,4,6,8,10,12}
set8.discard(6)
print(set8)

#set8.remove(1)
#print(set8) # give error if we want to remove element which not present
set8.discard(1) 
print(set8) # no error if we want to remove the element which is not present.

set9={10,20,30,40,50}
val=set9.pop() # pop() will remove randome num
print(val) #ouput : 50
print(set9) # output: {20, 40, 10, 30}

set10={ 5,10,15,20,25,30 }
set10.clear() # clear() to empty set.
print(set10)

# Frozen sets in python.

# * immutable # cannot add, remove ,change element
fset=frozenset([1,4,3,2,0])
print(fset) # o/p frozenset({0, 1, 2, 3, 4})

set={0,9,8,7,6,5,4}
set11=frozenset(set) 
print(set11) #o/p frozenset({0, 4, 5, 6, 7, 8, 9})

# typecasting objects into set using set()
# convering list into set
li=[5,4,3,2,1,0]
set11=set(li)
print(set11)  #o/p : {0, 1, 2, 3, 4, 5}

# convert string into set

strr="maheboobali"
set12=set(strr)
print(set12) #o/p {'a', 'l', 'h', 'b', 'i', 'm', 'o', 'e'}

dic={1:"one",2:"two",3:"three",4:"four"}
set22=set(dic)
print(set22)  # o/p: {1, 2, 3, 4}

set23=set22.copy() #copy whole set
print(set23)  # o/p: {1, 2, 3, 4}

a={1,2,3,4}
b={5,6,7,8}
c={11,12,13,14}
print(a.union(b)) # {1, 2, 3, 4, 5, 6, 7, 8}
print(a.union(b).union(c)) # {1, 2, 3, 4, 5, 6, 7, 8, 11, 12, 13, 14}
print(a.union(b,c)) # {1, 2, 3, 4, 5, 6, 7, 8, 11, 12, 13, 14}






