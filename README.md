a=(1,2,3,4,5)
print(a)
print(type(a))
print(a[1])
print(a[3])
b=(1,5,4,2,1,5)
print(b)
#b[1]=10 # it wont support change of element
print(b)

print(b[0])
print(b[1])
print(b[2])
print(b[-1])
print(b[-2])
print(b[-3])
print(b[::-1])
print(b[:4])
print(b[1:])

c=(21,22,23,24,25)
for num in c:
 print(num)
 
d=(2,4,8,12)
e=("cool","patience")
print(d+e)
f=(d,e)
print(f)

g=("hello",)*3
print(g)
print(len(g))

h=[5,4,3,2,1]
i=tuple(h)
print(i)

tup=("abc",)
n=5
for i in range(int(n)):
    tup=(tup,)
    print(tup)
    
tup1=("aland","gulbarga")
print(tup1)

tup2= 2,4,6
print(tup2)

x=tuple([3,5,6,7])
print(x)

tup3=(10,)
print(tup3)
print(type(tup3))
tup4=(10)
print(type(tup4))

a,b,c=10,20,30  # tuple packing
tup=(a,b,c)
print(tup)

z=[41,42,43,44,44,46,47,48]
ind=z.index(46,1,6)
print(ind)

x=z.count(44)
print(x)




 



