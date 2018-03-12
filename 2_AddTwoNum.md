# #2 Add Two Numbers

下面的方法是脑子中的第一反应，测试实例也能跑的通。但是题目中是使用Python链表，所以需要另想办法。

``` python
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution(object):
    def addTwoNumbers(self, l1, l2):
        """
        :type l1: ListNode
        :type l2: ListNode
        :rtype: ListNode
        """
        l1 = l1[::-1]
        l2 = l2[::-1]
        sum = {}
        adder = 0
        for i,num in enumerate(l1):
            sum[i] = num + l2[i] + adder
            if sum[i] >= 10:
                sum[i] = sum[i] - 10
                adder = 1
            else:
                adder = 0
        
        return sum
```

``` python
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution(object):
    def addTwoNumbers(self, l1, l2):
        """
        :type l1: ListNode
        :type l2: ListNode
        :rtype: ListNode
        """
        carry = 0
        root = n = ListNode(0)
        # 定义链表header
        while l1 or l2 or carry:
            v1 = v2 = 0
            if l1:
                v1 = l1.val
                l1 = l1.next
            if l2:
                v2 = l2.val
                l2 = l2.next
            carry, val = divmod(v1+v2+carry, 10)
            n.next = n = ListNode(val)
            #将每组对应数据添加到链表
        return root.next
	#输出链表

```
