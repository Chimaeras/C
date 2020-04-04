## 和为零的N个唯一整数
#### 给你一个整数 n，请你返回 任意 一个由 n 个 各不相同 的整数组成的数组，并且这 n 个数相加和为 0 。

---
* #### 解法1：
```
class Solution 
{
public:
    vector<int> sumZero(int n) 
    {
        vector<int> res;
        if(n==1)//长度为1，直接返回0
        {
            res.push_back(0);
        }
        else
        {
            int sum=0;
            for(int i=0;i<n-1;i++)//以此添加前n-1个数
            {
                res.push_back(i);
                sum=sum+i;//记录总和sum
            }
            res.push_back(0-sum);//添加总和的相反数-sum
        }
        return res;
    }
};

```

```
class Solution 
{
public:
    vector<int> sumZero(int n) 
    {
        vector<int> res;
        res.push_back((n*n-n)/2);//添加前n项和
        int tmp = -1 *n + 1;//第n项
        for(int i = tmp; i < 0;i++ )
            res.push_back(i);
        return res;
    }
};
```
