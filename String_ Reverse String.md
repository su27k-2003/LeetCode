Write a function that reverses a string. The input string is given as an array of characters s.

You must do this by modifying the input array in-place with O(1) extra memory.

 
```
Example 1:

Input: s = ["h","e","l","l","o"]
Output: ["o","l","l","e","h"]

Example 2:

Input: s = ["H","a","n","n","a","h"]
Output: ["h","a","n","n","a","H"]
``` 

Constraints:

1 <= s.length <= 105
s[i] is a printable ascii character.


Solution 1 - Reverse function
```
class Solution:
    def reverseString(self, s: List[str]) -> None:
        """
        Do not return anything, modify s in-place instead.
        """
        s.reverse()
```
Time: O(n), Space: O(1)

Solution 2 - Two pointer:
```
class Solution:
    def reverseString(self, s: List[str]) -> None:
        """
        Do not return anything, modify s in-place instead.
        """
        l, r = 0, len(s)-1
        
        while l < r:
            s[l], s[r] = s[r], s[l]
            l +=1
            r -=1
```
Time: O(n), Space: O(1)

Solution 3 - One pointer:
```
class Solution:
    def reverseString(self, s: List[str]) -> None:
        """
        Do not return anything, modify s in-place instead.
        """
        for i in range(len(s)//2):
            s[i], s[-i-1] = s[-i-1], s[i]
```
Time: O(n), Space: O(1)

Solution 4 - Stack (FILO), tradeoff Space: O(n)
```
class Solution:
    def reverseString(self, s: List[str]) -> None:
        """
        Do not return anything, modify s in-place instead.
        """
        stack =[]
        
        for i in s:
            stack.append(i)
            
        j = 0
        while stack:
            s[j] = stack.pop()
            j +=1
```
Time: O(n), Space: O(n)
