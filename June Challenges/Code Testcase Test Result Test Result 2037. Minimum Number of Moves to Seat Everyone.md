Difficulty : Easy 

https://leetcode.com/problems/minimum-number-of-moves-to-seat-everyone/description/?envType=daily-question&envId=2024-06-13

```python
class Solution:
    def minMovesToSeat(self, seats: List[int], students: List[int]) -> int:
        return sum([abs(sorted(seats)[i] - sorted(students)[i]) for i in range(len(seats))])
```
