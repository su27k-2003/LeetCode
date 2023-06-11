Given a string s, return true if the s can be palindrome after deleting at most one character from it.
 
```
Example 1:

Input: s = "aba"
Output: true

Example 2:

Input: s = "abca"
Output: true
Explanation: You could delete the character 'c'.
Example 3:

Input: s = "abc"
Output: false
``` 

Constraints:

1 <= s.length <= 105
s consists of lowercase English letters.

Solution:
```
class Solution:
    def isPalindrome(self, s: str) -> bool:
        s = re.sub("[^a-z | ^0-9]", "", s.lower())
        
        l, r = 0, len(s)-1
        
        while l < r:
            if s[l] != s[r]:
              skip_l, skip_r = s[l+1:r+1], s[l:r]
              return (skip_l == skip_l[::-1] or skip_r == skip_r[::-1])
            l, r = l+1, r-1
        return True
```
