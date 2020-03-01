## 数组拆分I
#### 题目：给定长度为2n的数组,你的任务是将这些数分成 n 对, 例如 (a1, b1),(a2,b2),...,(an,bn)，使得从1 到 n 的 min(ai, bi) 总和最大
---
* #### 解法1：
```
public:
    int arrayPairSum(vector<int>& nums) 
    {
        int sum=0;
        sort(nums.begin(),nums.end());
        for(int i=1;i<=nums.size();i=i+2)
        {
           sum=sum+min(nums[i-1],nums[i]);
        }
        return sum;
    }

```
* ##### 分析：将数组从小到大排序，sum依次加上min(ai,bi)，总和即为最大。
---
* #### 解法2：
```
 public:
    int arrayPairSum(vector<int>& nums) 
    {
        sort(nums.begin(),nums.end());
        int sum = 0;
        for(int i = 0;i < nums.size() / 2;i++)
        {
            sum += nums[2*i];
        }
        return sum;
    }
```
* ##### 分析：同理