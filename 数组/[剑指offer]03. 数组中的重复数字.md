## 题目描述

在一个长度为 n 的数组 nums 里的所有数字都在 0～n-1 的范围内。数组中某些数字是重复的，但不知道有几个数字重复了，也不知道每个数字重复了几次。请

找出数组中任意一个重复的数字。 

**示例 1：**

    输入：[2, 3, 1, 0, 2, 5, 3]
    输出：2 或 3 


限制： 

`2 <= n <= 100000 ` 


## 思路

数字都在 0～n-1 的范围内，因此如果不重复的话，第i个位置上的数字应该是i。

利用这个规律，遍历数组，将数字 i 放到第 i 个位置上，如果遇到了重复的则返回该数。

## code

```python
class Solution(object):
    def findRepeatNumber(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        i = 0
        while i < len(nums):
            if i < nums[i]:
                tmp = nums[i]
                if nums[tmp] == tmp:
                    return tmp
                nums[i] = nums[tmp]
                nums[tmp] = tmp
            elif i == nums[i]:
                i += 1
            else:
                return nums[i]
<<<<<<< HEAD
```
=======
```
>>>>>>> f16f325c948df99ec99f0472b23a7c55bf1f8584
