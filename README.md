# Plindromes

***Project Euler #4*** - largest palindrome of two 3 - digit numbers.

***Palindrome:*** A palindrome is a number that is the same backwards and forwards, like 101 or 990099



### Console log


> using indexedDB for stdlib modules cache

> ('palindrome:', 906609, 'digit:', 913, 'palindrome/digit:', 993.0, 'iterations:', 2136) Average run-time: 0.06740000247955322

> ('palindrome:', 906609, 'digit:', 913, 'palindrome/digit:', 993.0, 'iterations:', 2136) Average run-time: 0.06000001430511474



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
 

    


palindrome()
palindrome_back()

```