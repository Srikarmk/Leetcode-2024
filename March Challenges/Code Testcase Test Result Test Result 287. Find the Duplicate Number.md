Difficulty : Medium 

https://leetcode.com/problems/find-the-duplicate-number/description/?envType=daily-question&envId=2024-03-24 

```python
class Solution:
    def findDuplicate(self, nums: List[int]) -> int:
        for i in range(len(nums)):
            ind = abs(nums[i])
            if nums[ind] < 0:
                return ind
            nums[ind] = -nums[ind]
        return -1
```
