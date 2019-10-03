# 5. Longest Palindromic Substring

Given a string **s**, find the longest palindromic substring in **s**. You may assume that the maximum length of **s** is 1000.

**Example 1:**

```
Input: "babad"
Output: "bab"
Note: "aba" is also a valid answer.
```

**Example 2:**

```
Input: "cbbd"
Output: "bb"
```

---

```
class Solution(object):
    def longestPalindrome(self, s):
        """
        :type s: str
        :rtype: str
        """
        s_len = len(s)
        max_sub_s = ''
        for i in range(s_len):
            if len(max_sub_s) > (s_len - i):
                break
            for j in range(s_len,i,-1):
                sub_s = s[i:j]
                if sub_s == sub_s[::-1] and len(sub_s) > len(max_sub_s):
                    max_sub_s = sub_s
                    break
        
        return max_sub_s
```
