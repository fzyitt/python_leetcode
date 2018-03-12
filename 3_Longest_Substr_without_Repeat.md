# #3 Longest Substring Without Repeating Characters

此题最终目的在于判断原最长子数列和现最长子序列哪个更加长，因此要找到原最长子序列的末尾--res以及
现最长子序列的开头--start。

res为开头到出现重复字符的长度
start为重复字符的后一位

``` python
class Solution(object):
    def lengthOfLongestSubstring(self, s):
        """
        :type s: str
        :rtype: int
        """
        dic = {}
        res = 0
        start = 0
        for i, elem in enumerate(s):          
            if elem in dic:
                res = max(res, i-start)
                start = max(start, dic[elem]+1)
            dic[elem] = i
        return max(res, len(s)-start)
```


