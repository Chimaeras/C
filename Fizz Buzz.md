## FizzBuzz
#### 写一个程序，输出从 1 到 n 数字的字符串表示。

* 如果 n 是3的倍数，输出“Fizz”；

* 如果 n 是5的倍数，输出“Buzz”；

* 如果 n 同时是3和5的倍数，输出 “FizzBuzz”。


---
* #### 解法1：匹配到后直接返回
```
class Solution 
{
public:
    vector<string> fizzBuzz(int n) 
    {
        vector<string> res;
        for (int i = 1; i <= n; i++) 
        {
            if (i % 15 == 0) res.emplace_back("FizzBuzz");
            else if (i % 3 == 0) res.emplace_back("Fizz");
            else if (i % 5 == 0) res.emplace_back("Buzz");
            else res.emplace_back(to_string(i));
        }
        return res;
    }
};
```
---
* #### 解法2：逐步匹配（使用于规则更加复杂的情况）
```
//
class Solution 
{
public:
    vector<string> fizzBuzz(int n) 
    {
        vector<string> res;
        for(int i = 1; i <= n; i++)
        {
            string tmp;
            if(i % 3 == 0)
                tmp += "Fizz";
            if(i % 5 == 0)
                tmp += "Buzz";
            if(tmp.size() == 0)
                tmp = to_string(i);
            res.push_back(tmp);
        }
        return res;
    }
};
```



