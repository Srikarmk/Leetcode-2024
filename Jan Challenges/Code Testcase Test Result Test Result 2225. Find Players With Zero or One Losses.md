Difficulty : Medium 

https://leetcode.com/problems/find-players-with-zero-or-one-losses/description/?envType=daily-question&envId=2024-01-15 

```python
class Solution:
    def findWinners(self, matches):
        lost = defaultdict(int)
        
        for m in matches:
            lost[m[0]] += 0
            lost[m[1]] += 1
        
        zero = sorted([k for k, l in lost.items() if l == 0])
        ones = sorted([k for k, l in lost.items() if l == 1])
        
        return [zero, ones]
```
