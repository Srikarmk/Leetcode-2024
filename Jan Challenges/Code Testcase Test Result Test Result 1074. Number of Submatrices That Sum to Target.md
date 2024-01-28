Difficulty : Hard 

https://leetcode.com/problems/number-of-submatrices-that-sum-to-target/description/?envType=daily-question&envId=2024-01-28 


```python
from typing import List

class Solution:
    def numSubmatrixSumTarget(self, matrix: List[List[int]], target: int) -> int:
        m, n = len(matrix), len(matrix[0])
        for i in range(m):
            for j in range(1, n):
                matrix[i][j] += matrix[i][j - 1]

        result = 0
        for col1 in range(n):
            for col2 in range(col1, n):
                counter = {0: 1}
                current_sum = 0
                for row in range(m):
                    if col1 == 0:
                        current_sum += matrix[row][col2]
                    else:
                        current_sum += matrix[row][col2] - matrix[row][col1 - 1]
                    if current_sum - target in counter:
                        result += counter[current_sum - target]
                    counter[current_sum] = counter.get(current_sum, 0) + 1

        return result
```
