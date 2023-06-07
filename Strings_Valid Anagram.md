Given two strings s and t, return true if t is an anagram of s, and false otherwise.

An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

 
```
Example 1:

Input: s = "anagram", t = "nagaram"
Output: true

Example 2:

Input: s = "rat", t = "car"
Output: false
``` 

Constraints:

1 <= s.length, t.length <= 5 * 104
s and t consist of lowercase English letters.
 

Follow up: What if the inputs contain Unicode characters? How would you adapt your solution to such a case?

Solution 1: Use Counter function
```
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        return Counter(s) == Counter(t)
```
Time: O(s+t), space: O(s+t)

Solution 2: Build Hashmap
```
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        if len(s) != len(t):
            return False
        
        count_s, count_t = {}, {}
            
        for i in range(len(s)):
            if s[i] not in count_s:
                count_s[s[i]] = 1
            else:
                count_s[s[i]] += 1
                
            if t[i] not in count_t:
                count_t[t[i]] = 1
            else:
                count_t[t[i]] += 1
                
        return count_s == count_t 
```
Time: O(s+t), space: O(s+t)

Solution 3: How to use less space or if the string contain Unicode characters?
```
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        return sorted(s) == sorted(t)
```
Time: O(nlogn), space: O(1)
