## 重复N次的元素
#### 题目：在大小为2N的数组A中有N+1个不同的元素，其中有一个元素重复了N次，返回重复了N次的那个元素
---
* #### 解法1：
```
public:
    int repeatedNTimes(vector<int>& A) 
    {
        int len=A.size(),x,i=0;
        sort(A.begin(),A.end());
        while(i<len-1)
        {
            if(A[i]==A[i+1]) {x=A[i];break;}
            i++;
        }
        return x;
    }
```
* ##### 分析:对数组进行排序可知，只有一个元素重复了N次，故只要找到两个元素相等，即为目标元素。
---
* #### 解法2：
```
public:
    int repeatedNTimes(vector<int>& A) 
   {
        unordered_set<int> s;		
        for(int i=0; i<A.size(); i++)
        {
            if(s.find(A[i]) != s.end())
                return A[i];
            s.insert(A[i]);
        }
        return 0;
    }
```
* ##### 分析：二叉树查找 未学 挖坑
---
* #### 解法3：
```
public:
    int repeatedNTimes(vector<int>& A)
    {
        int i = 0, j = 0, n = A.size();
        while (i == j || A[i] != A[j])  //若i==j或者A[i] != A[j]，则重新抽取
            i = rand() % n, j = rand() % n;
        return A[i];
    }
```
* ##### 分析：随机抽取i和j，若A[i]==A[j],则返回A[i]。