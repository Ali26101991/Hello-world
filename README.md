# Python Lists 

a = [10, 20, "GfG", 40, True]  # example of List
print(a)
print(a[0])
print(a[1])
print(a[2])
print(a[3])
print(a[4])
print(type(a[0]))  # to know type of list item
print(type(a[2]))
print(type(a[4]))
b=["all","the","best"]  # string list
c=[1,2,3,4,5,6]  # integer list
d=["abc",40,30,True ]  # mixed list
print(b)
print(c)
print(d)

# We can create a list with repeated elements using the multiplication operator.
a=[2]*5  #create list with int 2 for 5 items
b=[0]*7  #create list with 0 for 7 items
print(a)
print(b)
print(d[0])
print(d[-1])

# use of append, insert and extend.
a=[]
a.append(10)
print(a)
a.insert(2,5)
print(a)
a.extend([20,30,40])
print(a)

x=[5,10,15,20,25,30]
x[1]=25  #adding element in list
x[3]=40
print(x)
x.remove(30)  # to remove element from list
print(x)
x.remove(40)
print(x)
x.pop(2) # removing by using index value
print(x)
del x[0] # deleting using index using del
print(x)

#access list using for loop.
y=[100,200,300,400,500]
for items in y:
    print(items)

# Nested loop and acessing them
    
z=[[1,2,3],[4,5,6],[7,8,9]]
element=z[0][2]  # sublist and element (o/p 3)
print(element)
element=z[1][2]
print(element)
element=z[2][2]
print(element)

for items in z:
    
    for things in items:
        print(things)
        


