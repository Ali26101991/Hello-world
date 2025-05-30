
#string slicing examples

s="Happynewyear"
print(s[1:3]) #it will print index1 to 2
print(s[:3]) #it will print till index  2
print(s[3:]) #it will print ind3 to last
print(s[::-1]) # it will reverse the string.

# strings are immutable and connot be change.
print("m"+s[1:]) #we can add and create new string
s1=s.replace("year","month") #replacing string.
print(s1)

print(len(s))  # indicated total character in strn
print(s.upper()) # to convert to upper case
print(s.lower()) # to convert to lower layer

print(s.strip()) #  remove white spaces
s3=s+s1  # concatinating strings
print(s3)

print(s *3)    #ing string using * operator.

del s  # for deleting entire string

location= "hyd"
state = "telangana"
print(f"{location},{state}") # f string use
print(f"city={location},softarea={state}") # f string usage

m=("i am living in {} from past {} years".format("hydrabad",5)) # .format use to add values  to strings
print(m)

print("gana" in state) #to check string presence
print("hyd" in state) # use of in function

