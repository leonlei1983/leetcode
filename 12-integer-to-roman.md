# 12. Integer to Roman

Roman numerals are represented by seven different symbols: `I`, `V`, `X`, `L`, `C`, `D` and `M`.

```
Symbol       Value
I             1
V             5
X             10
L             50
C             100
D             500
M             1000
```

For example, two is written as `II` in Roman numeral, just two one's added together. Twelve is written as, `XII`, which is simply `X` + `II`. The number twenty seven is written as `XXVII`, which is `XX` + `V` + `II`.

Roman numerals are usually written largest to smallest from left to right. However, the numeral for four is not `IIII`. Instead, the number four is written as `IV`. Because the one is before the five we subtract it making four. The same principle applies to the number nine, which is written as `IX`. There are six instances where subtraction is used:

- `I` can be placed before `V` (5) and `X` (10) to make 4 and 9. 
- `X` can be placed before `L` (50) and `C` (100) to make 40 and 90. 
- `C` can be placed before `D` (500) and `M` (1000) to make 400 and 900.
Given an integer, convert it to a roman numeral. Input is guaranteed to be within the range from 1 to 3999.

**Example 1:**
```
Input: 3
Output: "III"
```

**Example 2:**
```
Input: 4
Output: "IV"
```

**Example 3:**
```
Input: 9
Output: "IX"
```

**Example 4:**
```
Input: 58
Output: "LVIII"
Explanation: L = 50, V = 5, III = 3.
```

**Example 5:**
```
Input: 1994
Output: "MCMXCIV"
Explanation: M = 1000, CM = 900, XC = 90 and IV = 4.
```
---

```
class Solution(object):
    def intToRoman(self, num):
        """
        :type num: int
        :rtype: str
        """
        result = ''
        
        m_c = num / 1000
        remind = num % 1000
        result += 'M' * m_c
        
        if remind >= 900:
            remind %= 900
            result += 'CM'
        
        if remind >= 500:
            remind %= 500
            result += 'D'
        
        if remind >= 400:
            remind %= 400
            result += 'CD'
        
        c_c = remind / 100
        remind = remind % 100
        result += 'C' * c_c
        
        if remind >= 90:
            remind %= 90
            result += 'XC'
        
        if remind >= 50:
            remind %= 50
            result += 'L'
        
        if remind >= 40:
            remind %= 40
            result += 'XL'
        
        x_c = remind / 10
        remind = remind % 10
        result += 'X' * x_c
        
        if remind >= 9:
            remind %= 9
            result += 'IX'
        
        if remind >= 5:
            remind %= 5
            result += 'V'
        
        if remind >= 4:
            remind %= 4
            result += 'IV'
        result += 'I' * remind
        return result
```
