# Plindromes

***Project Euler #4*** - largest palindrome of two 3 - digit numbers.

***Palindrome:*** A palindrome is a number that is the same backwards and forwards, like 101 or 990099



### Console log


> using indexedDB for stdlib modules cache

> ('palindrome:', 906609, 'digit:', 913, 'palindrome/digit:', 993.0, 'iterations:', 2136) Average run-time: 0.06740000247955322

> ('palindrome:', 906609, 'digit:', 913, 'palindrome/digit:', 993.0, 'iterations:', 2136) Average run-time: 0.06000001430511474

------

### Codes are used

```py

import time

def is_palindrome(val):
    val = str(val)
    if val == val[::-1]:
        return(True)
    else:
        return(False)
#def is_palindrome(val):
 #   return str(val) == str(val)[::-1]
 
def palindrome():
    start_time = time.time()
    palindromes_list=[]
    debug_list=[]
    low_val =900
    high_val = 999
    iterations = 0
    
    for num1 in range(low_val,high_val):
        for num2 in range(low_val,high_val):
            iterations += 1
            #print(num1,num2)
            if is_palindrome(num1*num2):
                palindromes_list.append(num1*num2)
                debug_list.append([num1,num2,num1*num2])
            if num1 == num2:
                break
    print('print of palindromes:',palindromes_list, num1, num2)
    print('debug_list:', debug_list)
    print('Iterations:' , iterations)
    print('Largest palindrome:', max(palindromes_list))
    print('Runtime:', time.time()-start_time)
    print('---------End Run--------') #110 seconds, 55 secs
    
def palindrome_back():
    start_time = time.time()
    palindromes_list=[]
    debug_list=[]
    low_val =100
    high_val = 999
    iterations = 0
    low_num2_val =100
    
    for num1 in range(high_val,low_val,-1):
        if num1 < low_val:
            break
        for num2 in range(high_val,low_num2_val,-1):
            iterations += 1
            #print(num1,num2)
            if is_palindrome(num1*num2):
                palindromes_list.append(num1*num2)
                low_val = max((num1*num2)/high_val,low_val)
                low_num2_val = num2
                debug_list.append([num1,num2,(num1*num2)/high_val,low_val])
            if num1 == num2:
                break
    print('print of palindromes:',palindromes_list, num1, num2)
    print('debug_list:', debug_list)
    print('Iterations:' , iterations)
    print('Largest palindrome:', max(palindromes_list))
    print('Runtime:', time.time()-start_time)
    print('---------End Run--------') #110 seconds, 55 secs

    
palindrome()
palindrome_back()

```