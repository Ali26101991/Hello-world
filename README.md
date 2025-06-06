dic ={ 1:"jan",2:"feb",3:"mar"}
print(dic)    # dictionary

d2= dict(a = "crow",b = "eagle",c = "croco")
print(d2)

d2["age"]=22  # add into dictionary 
d2[1]="hello"  # add into dictionary

print(d2)

d3={"name":"ali",1:"number",(1,2):[1,2,4]}
# below are example for access dic elements.
print(d3)
print(d3["name"]) 
print(d3.get("name"))  # using get()
print(d3.get(1))
print(d3.get((1,2)))
print(d3[1])
print(d3[(1,2)])

d4={ "game":"cricket","work":"engineer",3:"hello"}
print(d4)
del d4["work"]  # to delete element.
print(d4)
val=d4.pop(3) # 
print(val)
print(d4)
d4.popitem()
d5={101:"mon",102:"tue",103:"wed",104:"thu"}
print(d5)
value=d5.popitem() # return last inserted key and value
print(value)
d5[105]="fri"
print(d5)
print(d5.popitem())
d6={1:"jan",2:"feb",3:"mar",4:"april"}
key,value=d6.popitem() 
print(key)
print(value)
d6.clear()
print(d6)
d7={1:"jan",2:"feb",3:"mar",4:"april"}
for key in d7:  
 print(key)  # prints key only
for value in d7.values():
    print(value)  # print value only
for key,value in d7.items(): 
    print(f"{key}={value}") #print key and value

d8={2:"two",3:"three",4:"four",5:{"a":"abc","b":"cba"}}  # nested dictionary
print(d8)





