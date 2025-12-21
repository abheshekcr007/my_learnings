Assume "#" is like a backspace in string. This means that string "a#bc#d" actually is "bd"  

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
        
        
    
        
    
    
        
    
