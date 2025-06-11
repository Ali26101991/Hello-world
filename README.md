
# python loop :  while 
cnt=0
while cnt<3:
    cnt+=1
    print("hello world")
 
# using while and else  
    
num=0
while num<8:
    num+=2
    print("yes got it")
else:
    print("loop over")

# Below is infinite loop
    
#num=0
#while (num==0):
    #print("hello")
    
li=[2,4,5,5,6]
for i in li:
    print(i)
    
str="votaytech"
for x in str:
    print(x)
    
for x in range(0,9):
    print(x)
    
for y in range(20):
    if y % 2 ==0:
        print(y)
        
tup=(5,10,15,20,25,30)
for a in tup:
    print(a)
    
li=[4,8,12,24]
for x in range(len(li)):
    print(x,li[x])
    
x=4
for x in range(0,x):
    print(x)
    
list1=["book","pencil","paper"]
for x in list1:
    print(x)

tup=("pc","monitor","mouse")
for x in tup:
    print(x)
    
dic=dict({"x":123,"y":456})
print(dic)
for i in dic:
    print(i,dic[i])

set1={20,30,40,50,60}
for i in set1:
    print(i)
    
for i in range(1,5):
    for j in range(i):
        print(i, end=" ")
    print()
    
######### using break #######   
for letter in "maheboobali":
    if letter=="l" or letter=="i":
        break
print("curent letter is :", letter)

########## using continue ############
for letter in "maheboobali":
    if letter=="l" or letter=="i":
        continue
    print(letter)
    
##### using pass ############   
for i in "maheboobali":
    pass
print(i)
    

    
    
    
    
