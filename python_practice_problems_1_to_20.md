1.Assume "#" is like a backspace in string. This means that string "a#bc#d" actually is "bd"  

Your task is to process a string with "#" symbols.  

Examples
"abc#d##c"      ==>  "ac"  
"abc##d######"  ==>  ""  
"#######"       ==>  ""  
""              ==>  ""  

```
def clean_string(s):
    # your code here
    #iterate over the list
    #if an element is equal to # ..remove that element and also
    #the previous non # element
    #return the list that remains at last
    
    result=[]
    for i in s:
        if i == '#':
            if result:
                result.pop()
        else:
            result.append(i)
    return ''.join(result)
  ```      
        
2.valid ip or not   

Examples of valid inputs:  
1.2.3.4  
123.45.67.89  
Invalid input examples:  
1.2.3  
1.2.3.4.5  
123.456.78.90  
123.045.067.089  
Notes:  
Leading zeros (e.g. 01.02.03.04) are considered invalid  
Inputs are guaranteed to be a single string  

```
   def is_valid_IP(strng):
    elem=strng.split(".")
    if len(elem) !=4:
        return False
    
    for i in elem:
        if not i.isdigit():
            return False
        j=int(i)
        if j<0 or j>255:
            return False
        if len(i)>1 and i[0]=="0":
            return False    
    return True
```

3.Given a non-empty array of integers, return the result of multiplying the values together in order. Example:

[1, 2, 3, 4] => 1 * 2 * 3 * 4 = 24  

```
from functools import reduce

def grow(arr):
    val = reduce(lambda x,y:x*y,arr)
    return val
```

4.student A comes opens all the doors 
Student 2 comes opens all the 2nd,4th,6th doors and so on   
Student 3 comes opens all the 3rd,6th,9th doors and so on  
there are N doors and N number of students  

this was my solution ..but gets timed out for larger numbers  

```
def doors(n):
    pass
#if a door is toggled odd number of times it remains open
#if its toggled even number of times ..it remains closed

    dict={}
    counter=0
    for i in range(1,n+1):
        count=1
        for j in range(1,i):
            if i%j ==0:
                count+=1
        dict[i]=count

    for key,value in dict.items():
        if value %2 !=0:
            counter+=1
    return counter
```

efficient solution-  

import math

```
def doors(n):
    limit =math.isqrt(n)
    return limit
    pass
```

5.You need to implement a function that validates a given Spanish DNI number. The function should return true/True if the DNI is valid and false/False otherwise.

DNI Format
A valid Spanish DNI follows this structure:

8 digits followed by 1 letter.
Example: 12345678A.
The letter is calculated based on the 8-digit number. The algorithm is as follows:

Divide the 8-digit number by 23.
The remainder of the division will correspond to a specific letter.
The correspondence between the remainder and the letter is fixed and follows a specific order.  

```
text,num_slice='TRWAGMYFPDXBNJZSQVHLCKE',s[:-1]
    if num_slice.isdigit() and text[int(num_slice)%23]==s[-1]:
        return True
    else:
        return False
```

6.Examples:

preferred	blacklisted	options	expected result
attack, defense	luck	(luck,25)→A
(speed,20)→B
(defense,15)→C	Should pick C: defense (the only preferred option available).
attack	luck, speed, defense	(luck,30)→A
(speed,20)→B
(defense,15)→C	Should return D: all options (A, B, C) are blacklisted, so fall back to D.
attack	luck	(luck,30)→A
(speed,20)→B
(defense,15)→C	Should pick B: speed (neutral) with the highest value among neutral skills.
attack, defense	luck	(attack,20)→A
(defense,20)→B
(speed,10)→C	Should pick A or B: both attack and defense are preferred and tied on value, so either A or B is acceptable.  

```
values=["A","B","C"]
    
    val = [(i[1],options.index(i)) for i in options if i[0] in preferred]
    val2=[(i[1],options.index(i)) for i in options if i[0] not in blacklisted]
    if val:
        highest=max(val,key=lambda x:x[0])
        return values[highest[1]]
    elif val2:
        highest=max(val2,key=lambda x:x[0])
        return values[highest[1]]
    else:
        return 'D'
```

7.Build a function that takes in two arguments (salary, bonus). Salary will be an integer, and bonus a boolean.

If bonus is true, the salary should be multiplied by 10. If bonus is false, the fatcat did not make enough money and must receive only his stated salary.  

```
def bonus_time(salary, bonus):
    #your code here
    if bonus:
        val=salary*10
        return f'${val}'
    else:
        return f'${salary}'
```

8.rock,paper,scissors  

```
def rps(p1, p2):
    #your code here
    arr=["rock","paper","scissors"]
    if p1==p2:
        return "Draw!"
    elif p1=="rock" and p2=="scissors":
        return "Player 1 won!"
    elif p1=="scissors" and p2=="paper":
        return "Player 1 won!"
    elif p1=="paper" and p2=="rock":
        return  "Player 1 won!"
    else:
        return "Player 2 won!"
```

9.sushi problem  

"rr"           -->  4     # 2 plates
"rr rrr"       -->  8     # 5 plates, 1 free
"rrrrr rrrrr"  -->  16    # 10 plates, 2 free  

```
def total_bill(s):
    # Code here
    print(s)
    arr = [i for i in s if i == 'r']
    print(arr)
    val = len(arr)/5
    val2=round(len(arr)//5)
    print(val)
    print(val2)
    return (len(arr)-val2)*2
```

10.
high_and_low("1 2 3 4 5") # return "5 1"
high_and_low("1 2 -3 4 5") # return "5 -3"
high_and_low("1 9 3 4 -5") # return "9 -5"

```
def high_and_low(numbers):
    # ...
    list = [int(i.strip()) for i in numbers.split(' ') if i.strip() !=""]
    return f"{max(list)} {min(list)}"
```

11.find the mine  

[ [1, 0, 0], [0, 0, 0], [0, 0, 0] ] --> [0, 0]  

[ [0, 0, 0], [0, 1, 0], [0, 0, 0] ] --> [1, 1]  

[ [0, 0, 0], [0, 0, 0], [0, 1, 0] ] --> [2, 1]  


```
def mine_location(field):
    arr = [[field.index(i),i.index(j)] for i in field for j in i if j ==1]
    for i in arr:
        return i
```

12.the length of each word does not exceed the amount of words in the string  

```
def is_kiss(words):
    val = [len(i) for i in words.split(' ')]
    if max(val)>len(val):
        return "Keep It Simple Stupid"
    else:
        return "Good work Joe!"
```

13.sumMul(2, 9)   ==> 2 + 4 + 6 + 8 = 20
sumMul(3, 13)  ==> 3 + 6 + 9 + 12 = 30
sumMul(4, 123) ==> 4 + 8 + 12 + ... = 1860
sumMul(4, -7)  ==> "INVALID"  

```
def sum_mul(n, m):
    if n>0 and m>0:
        sum=0
        for i in range(n,m,n):
            sum+=i
        print(n,m)
        return sum
    else:
        return 'INVALID'
```

14.ascending or descending  

```
def is_sorted_and_how(arr):
    # your code here
    if all(arr[i]>arr[i+1] for i in range(len(arr)-1)):
        return 'yes, descending'
    elif all(arr[i]<arr[i+1] for i in range(len(arr)-1)):
        return 'yes, ascending'
    else:
        return 'no'
```

15.You are given an array with several "even" words, one "odd" word, and some numbers mixed in.

Determine if any of the numbers in the array is the index of the "odd" word. If so, return true, otherwise false.  

```
def odd_ball(arr):
    list = [arr.index(i) for i in arr if i =='odd']
    if list[0] in arr:
        return True
    else:
        return False
```
16.palindrome  

```
def is_palindrome(s):
    val=s.lower()
    return val==val[::-1]
```

17.sort a list of dict ..and the sort key is also dynamically passed  

When sorted by "a", this:

[
  {"a": 1, "b": 3},
  {"a": 3, "b": 2},
  {"a": 2, "b": 40},
  {"a": 4, "b": 12}
]
should return:

[
  {"a": 4, "b": 12},
  {"a": 3, "b": 2},
  {"a": 2, "b": 40},
  {"a": 1, "b": 3}
]  

```
def sort_list(sort_by, lst):
    print(sort_by,lst)
    return sorted(lst,key=lambda x:x[sort_by],reverse=True)
```

18.most digits  

```
def find_longest(arr):
    #your code here
    val=[(len(str(i)),i) for i in arr]
    val2=max(val,key=lambda x:x[0])
    return val2[1]
    pass
```

19.[7] should return 7, because it occurs 1 time (which is odd).
[0] should return 0, because it occurs 1 time (which is odd).
[1,1,2] should return 2, because it occurs 1 time (which is odd).
[0,1,0,1,0] should return 0, because it occurs 3 times (which is odd).
[1,2,2,3,3,3,4,3,3,3,2,2,1] should return 4, because it appears 1 time (which is odd).  


```
def find_it(seq):
    dict={}
    for i in seq:
        if i in dict:
            dict[i]+=1
        else:
            dict[i]=1
    val=[key for key,value in dict.items() if value%2!=0]
    return val[0]
```

20.reverse fibonacci series  

```
def solution(first, second):
    list=[]
    list.append(first)
    list.append(second)
    
    while list[0]>=0:
        val=list[1]-list[0]
        list.insert(0,val)
    print(list)
    return (list[2],list[3])
```



        
    
    
        
    
