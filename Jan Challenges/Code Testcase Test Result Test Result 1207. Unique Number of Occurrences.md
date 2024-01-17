Difficulty : Easy 

https://leetcode.com/problems/unique-number-of-occurrences/description/?envType=daily-question&envId=2024-01-17 

```python
class Solution:
    def uniqueOccurrences(self, arr: List[int]) -> bool:
        frequency = {}

        for num in arr: # Store element and its frequency
            frequency[num] = frequency.get(num,0) + 1

        # True if we get n different frequency for n different numbers
        return len(frequency) == len(set(frequency.values()))
```
