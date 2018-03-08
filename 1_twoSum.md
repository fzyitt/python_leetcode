# #1 twoSum

Run a loop to get index and corresponding number in the array, then put the index into an empty array.

``` python
class Solution(object):
    def twoSum(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
        dic={}
        for i,num in enumerate(nums):
            if num in dic:
                return [dic[num], i]
            else:
                dic[target-num] = i
```
