## Python3版



## 01.数组

### 1.1.数组的遍历



####  [485. 最大连续 1 的个数](https://leetcode-cn.com/problems/max-consecutive-ones/)



简单遍历，内存开销大

```python3
class Solution(object):
    def findMaxConsecutiveOnes(self, nums):
        n=len(nums)
        count=0
        countmax=0
      
      for i in range(n):
            if (nums[i]==1):
                count=count+1
            else:
                count=0
           
           if(count>=countmax):#连续1个数大则更新
                countmax=count
                
        return countmax
```

#### [495. 提莫攻击](https://leetcode-cn.com/problems/teemo-attacking/)



注意中毒时间不可叠加

```python3
class Solution:
    def findPoisonedDuration(self, timeSeries: List[int], duration: int) -> int:
        sumTime=0
        poisoning=0
        
        for i in range(len(timeSeries)-1):
            poisoning=timeSeries[i]+duration
            
            if timeSeries[i+1]>poisoning:
                sumTime+=duration
            elif timeSeries[i+1]<=poisoning:
                sumTime+=timeSeries[i+1]-timeSeries[i]
                
        return sumTime+duration#注意加上最后中毒时间
```
