
#convering string into bytes
# utf-8 is default encoding method

a="hydrabaddd"
b=bytes(a,"utf-8")
print(b) #o/p : b'hydrabad'
c=bytes(a,"utf-16")
print(c) # b'\xff\xfeh\x00y\x00d\x00r\x00a\x00b\x00a\x00d\x00d\x00d\x00'

a=" happy new year "
b=bytes(a,"utf-8")
print(b)  # b' happy new year '

# converting list of intiger into bytes

a=[2,4,5,6,7]
b=bytes(a)
print(b) # b'\x02\x04\x05\x06\x07'

# creating bytes objects with specific size.

a=5 
b=bytes(a) # creating byte object of length 5
print(b) # b'\x00\x00\x00\x00\x00'

#bytearray 

a="all is well "
b=bytearray(a,"utf-8")
print(b) # output : bytearray(b'all is well ')
b[1]=105 # 105 is i in ASCII 
print(b) #(output :bytearray(b'ail is well ') )

c=bytearray()
print(c) # output : bytearray(b'')
print(len(c)) # output : 0
c.append(97)
print(c) # output : bytearray(b'a')


#Syntax of memory veiw is memoryview(object)

data=bytearray("hello","utf-8")
print(data)
mv=memoryview(data)
print(mv[0])
mv[0]=105
print(data)

data1=b'python'
mv=memoryview(data1)
print(mv[0])
print(mv[1])
print(mv[2])
print(mv[3]) # to access memmory view
print(mv[1:4].tobytes())  #to access bytes data
print(mv[:4].tobytes())
print(mv[::-1].tobytes())
print(mv[1:].tobytes())

