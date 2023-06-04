Given a signed 32-bit integer x, return x with its digits reversed. If reversing x causes the value to go outside the signed 32-bit integer range [-231, 231 - 1], then return 0.

Assume the environment does not allow you to store 64-bit integers (signed or unsigned).

 
```
Example 1:

Input: x = 123
Output: 321
Example 2:

Input: x = -123
Output: -321
Example 3:

Input: x = 120
Output: 21
``` 

Constraints:

-231 <= x <= 231 - 1

Solution 1:
```
class Solution:
    def reverse(self, x: int) -> int:
        num = 0
        a = abs(x)
        
        while(a != 0):
            temp = a % 10
            print('temp:', temp)
            num = num * 10 + temp
            print('num:', num)
            a = a // 10
            print('a:', a)
            
        if x > 0 and num < 2147483647:
            return num
        elif x < 0 and num <= 2147483647:
            return -num
        else:
            return 0
```
