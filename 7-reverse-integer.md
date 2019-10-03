# 7. Reverse Integer

Given a 32-bit signed integer, reverse digits of an integer.

**Example 1:**
```
Input: 123
Output: 321
```

**Example 2:**
```
Input: -123
Output: -321
```

**Example 3:**
```
Input: 120
Output: 21
```

**Note:**

Assume we are dealing with an environment which could only store integers within the 32-bit signed integer range: [−231,  231 − 1]. For the purpose of this problem, assume that your function returns 0 when the reversed integer overflows.

---
```
class Solution(object):
    def reverse(self, x):
        """
        :type x: int
        :rtype: int
        """
        max_n = 2**31
        if x > (max_n - 1) or x < - max_n:
            return 0
        
        reverse_x = int(str(abs(x))[::-1])
        reverse_x = reverse_x if x > 0 else - reverse_x
        
        if reverse_x > (max_n - 1) or reverse_x < - max_n:
            return 0
        return reverse_x
```
