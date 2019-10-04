# 11. Container With Most Water

Given n non-negative integers a<sub>1</sub>, a<sub>2</sub>, ..., a<sub>n</sub> , where each represents a point at coordinate (i, a<sub>i</sub>). n vertical lines are drawn such that the two endpoints of line i is at (i, a<sub>i</sub>) and (i, 0). Find two lines, which together with x-axis forms a container, such that the container contains the most water.

**Note:** You may not slant the container and n is at least 2.

**Example:**
```
Input: [1,8,6,2,5,4,8,3,7]
Output: 49
```

---

```
class Solution(object):
    def maxArea(self, height):
        """
        :type height: List[int]
        :rtype: int
        """
        s = 0
        e = len(height)-1
        max_area = 0
        while s < e:
            area = (e-s) * min(height[s], height[e])
            max_area = max(area, max_area)
            
            if height[s] <= height[e]:
                s += 1
            else:
                e -= 1
        return max_area
```
