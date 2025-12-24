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



        
    
    
        
    
