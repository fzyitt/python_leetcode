# #6 ZigZag Conversion


了解zigzag原理
```
*  *  *  ...
* ** **  ...
** ** *  ...
*  *  *  ...

```
``` python
class Solution(object):
    def convert(self, s, numRows):
        """
        :type s: str
        :type numRows: int
        :rtype: str
        """
        if numRows == 1 or numRows >= len(s):
            return s
        
        L = [''] * numRows
        index = 0
        step = 1
        
        for x in s:
            L[index] += x
            if index == 0:
                step = 1
            elif index == numRows - 1:
                step = -1
            index += step
            
        return ''.join(L)  
```

str.join(s)表示将s中的字符串中间添加str         
