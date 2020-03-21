## x的平方根
#### 题目：实现 int sqrt(int x) 函数。

计算并返回 x 的平方根，其中 x 是非负整数。

由于返回类型是整数，结果只保留整数的部分，小数部分将被舍去。

---
* #### 解法1：
```
class Solution {
public:
    int mySqrt(int x) {
        int sqrt=0;
        int i=1;
        if(x==0) return 0;//0的平方根为0
        while((x/i)>=i)
        {
            sqrt=i;//当i*i<x时，记录sqrt，不断更新知道i*i>x
            i++;
        }
        return sqrt;
    }
};
```
---
* #### 解法2：
```
class Solution {
public:
    int mySqrt(int x) {
        if(x==0) return 0;//0的平方根为0
        long left=1;
        long right=x;
        long middle =(left+right)/2;
        while(left<=right)//当左小于右
        {
            if(middle*middle<=x&&(middle+1)*(middle+1)>x)
            {
                return middle;//middle的平方大于等于左半边且小于右半边
            }
            else if((middle*middle)<x)//middle的平方小于目标值(过小了)
            {
                left=middle+1;//往右边移
                middle=(left+right)/2;
            }
            else//middle的平方大于目标值(过大了)
            {
                right=middle-1;//往左边移
                middle=(left+right)/2;
            }
        }
        return middle;
    }
};
```
