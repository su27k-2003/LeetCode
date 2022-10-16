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

Code 1 - Rotate k times:

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

Code 2 - Using Reverse
```python
class Solution:
    def rotate(self, nums, k) -> None:
        """
        :type nums: List[int]
        :type k: int
        :rtype: None Do not return anything, modify nums in-place instead.
        """
        k %= len(nums)
        self.reverse(nums,0,len(nums)-1)
        self.reverse(nums,0, k-1)
        self.reverse(nums,k, len(nums)-1)

    def reverse(self, nums, start, end) -> None:
        """
        :type nums: List[int]
        :type start: int
        :type end: int
        :rtype: None
        """
        while start < end: #
            temp = nums[start]
            nums[start] = nums[end]
            nums[end] = temp 
            start += 1
            end -= 1
```


Complexity Analysis:
- Code 1 - Rotate k times: O(n * k) in time, O(1) in space
- Code 2 - Using Reverse: O(n) in time, O(1) in space
