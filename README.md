# List comprehension

# syntax 1: [ expression for variable in iterable]
nums=[3,6,8,12,14,15]

lis=[]
for num in nums:
    lis.append(num*num)
print(lis)

print([num*num for num in nums ])

# syntax 2; if condition
# [expression for variable in iterable if cond]

nums=[5,4,3,8,12,15,14]
lis=[]
for num in nums:
    if num%2==0:
     lis.append(num*num)

print(lis)

print([num*num for num in nums if num%2==0])

# syntax 3 : nested if 
#[expression for varialble in iterable if cond1 if cond2]

nums=[5,4,3,8,12,15,14]
lis=[]
for num in nums:
    if num%2==0:
        if num%3==0:
          lis.append(num*num)

print(lis)

print([num*num for num in nums if num%2==0 if num%3==0 ])
# syntax :4
#[expression if cond else expression for variable in iterable ]

nums=[5,4,3,8,12,15,14]
result=[]
for num in nums:
    if num%2==0:
        print(result.append(num*num))
    else:
        print(result.append(num*num*num))
        
print(result)
print([num*num if num%2==0 else num*num*num for num in nums])

############################################
#syntax: 5
lis=[]
for i in range(3,6):
     for j in range(5,7):
         lis.append(i*j)
print(lis)
############# using list comprehension.
print([i*j for i in range(3,6) for j in range(5,7) ])
    
