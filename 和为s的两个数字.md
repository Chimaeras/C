## 和为s的两个数字
#### 输入一个递增排序的数组和一个数字s，在数组中查找两个数，使得它们的和正好是s。如果有多对数字的和等于s，则输出任意一对即可。
---
* #### 解法1：双指针
```
class Solution
 {
public:
    vector<int> twoSum(vector<int>& nums, int target) 
    {
     
        vector<int> res;
        int i = 0,j = nums.size() - 1;
        while(nums[j] >= target) //找到刚好大于target的数 减少次数
        {
            j--;
        }
        while(i <= j) 
        {
           if(nums[i] + nums[j] > target) //右指针往左移
           {
               j--;
           } 
           else if(nums[i] + nums[j] < target)//左指针往右移
           {
               i++;
           } 
           else 
           {
               res.push_back(nums[i]);
               res.push_back(nums[j]);
               break;
           }
        }
         return res;
    }
};

```
