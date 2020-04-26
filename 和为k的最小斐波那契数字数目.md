## 和为k的最少斐波那契数字数目
#### 给你数字 k ，请你返回和为 k 的斐波那契数字的最少数目，其中，每个斐波那契数字都可以被使用多次。
---
* #### 解法1：
```
class Solution 
{
public:
    int findMinFibonacciNumbers(int k) 
    {
        //思路：
        //1.先创建斐波那契数组直到最后一个数超过k
        //2.从后往前找到最大数，并用k减去该数值
        //3.依次往前

        vector<int> fib;
        int a=1,b=1;
        fib={a,b};//构建初始的fib
        while(a+b<=k)//不断迭代更新fib
        {
            fib.push_back(a+b);
            int c=a+b;
            a=b;
            b=c;
        }
        
        int count=0;int i=fib.size()-1;

        while(k>0)//从后往前贪心寻找
        {
            if(k>=fib[i])
            {
                k=k-fib[i];
                count++;    
            }
            i--;
        }
        return count;
    }
};

```

### 正确性证明
https://leetcode-cn.com/problems/find-the-minimum-number-of-fibonacci-numbers-whose-sum-is-k/solution/he-wei-k-de-zui-shao-fei-bo-na-qi-shu-zi-shu-mu-by/
