# #5 Longest Palindromic Substring

查找数组中最长的回文子字符串

- 长度可能为偶数和奇数
- 写个函数进行回文迭代
- res作为最大长度存储

``` python
class Solution(object):
    def longestPalindrome(self, s):
        """
        :type s: str
        :rtype: str
        """
        res = ""
        for i in range(len(s)):
            tmp = self.itera(s, i, i)
            if len(tmp) > len(res):
                res = tmp
            
            tmp = self.itera(s, i, i+1)
            if len(tmp) > len(res):
                res = tmp
        return res
            
            
    def itera(self, s, l, r):
        while l >= 0 and r < len(s) and s[l] == s[r]:
            l -= 1 
            r += 1
        return s[l+1:r]
```


