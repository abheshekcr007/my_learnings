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




        
    
    
        
    
