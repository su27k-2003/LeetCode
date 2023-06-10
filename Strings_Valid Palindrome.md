A phrase is a palindrome if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward. Alphanumeric characters include letters and numbers.

Given a string s, return true if it is a palindrome, or false otherwise.

 
```
Example 1:

Input: s = "A man, a plan, a canal: Panama"
Output: true
Explanation: "amanaplanacanalpanama" is a palindrome.
Example 2:

Input: s = "race a car"
Output: false
Explanation: "raceacar" is not a palindrome.
Example 3:

Input: s = " "
Output: true
Explanation: s is an empty string "" after removing non-alphanumeric characters.
Since an empty string reads the same forward and backward, it is a palindrome.
``` 

Constraints:

1 <= s.length <= 2 * 105
s consists only of printable ASCII characters.

Solution 1: Use extra space
```
class Solution:
    def isPalindrome(self, s: str) -> bool:
        new_str = ""
        
        for i in s:
            if i.isalnum():
                new_str += i.lower()
        return new_str == new_str[::-1]
```
Time: O(n), space: O(n)

Solution 2: two pointer with re.sub
```
lass Solution:
    def isPalindrome(self, s: str) -> bool:
        s = re.sub("[^a-z | ^0-9]", "", s.lower())
        l, r = 0, len(s)-1
        
        while l < r:
            if s[l] != s[r]:
                return False
            l, r = l+1, r-1
        return True
```
Time: ?, Space: O(1)

Solution 3: two pointer without re.sub
```
class Solution:
    def isPalindrome(self, s: str) -> bool:
    
        l, r = 0, len(s)-1
        
        while l < r:
            while l<r and not self.isAlphaNum(s[l]):
                l +=1
            while l<r and not self.isAlphaNum(s[r]):
                r -=1
            if s[l].lower() != s[r].lower():
                return False
            l, r = l+1, r-1
        return True
    
    def isAlphaNum(self,i):
        return (ord('A') <= ord(i) <= ord('Z') or
                ord('a') <= ord(i) <= ord('z') or 
                ord('0') <= ord(i) <= ord('9'))
```
Time: O(n), space: O(1)
