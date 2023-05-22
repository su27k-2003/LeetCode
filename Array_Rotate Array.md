# Rotate Array
Given an array, rotate the array to the right by k steps, where k is non-negative.

Example 1:

```
Input: nums = [1,2,3,4,5,6,7], k = 3
Output: [5,6,7,1,2,3,4]
Explanation:
rotate 1 steps to the right: [7,1,2,3,4,5,6]
rotate 2 steps to the right: [6,7,1,2,3,4,5]
rotate 3 steps to the right: [5,6,7,1,2,3,4]
```

Example 2:

```
Input: nums = [-1,-100,3,99], k = 2
Output: [3,99,-1,-100]
Explanation: 
rotate 1 steps to the right: [99,-1,-100,3]
rotate 2 steps to the right: [3,99,-1,-100]
```

Solution 1 - Rotate k times:

```python
class Solution:
    def rotate(self, nums: List[int], k: int) -> None:
        """
        Do not return anything, modify nums in-place instead.
        """
        for i in range(k):
            nums.insert(0, nums.pop())
        return nums

```
Complexity: O(n * k) in time, O(1) in space

Solution 2 - Using Reverse
```python
class Solution:
    def rev(nums, l, r):
        while l < r:
            nums[l], nums[r] = nums[r], nums[l]
            l+=1
            r-=1
   
   n = len(nums)
   k %= n
   
   rev(nums, 0, n-1)
   rev(nums, 0, k-1)
   rev(nums, k, n-1)
```

Complexity: O(n) in time, O(1) in space
