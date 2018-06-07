# Practice
反转字符串
## 问题
#### 
请编写一个函数，其功能是将输入的字符串反转过来。
## 编程实现：
class Solution {
public:

    string reverseString(string s) 
    {
       reverse(s.begin(),s.end());
        return s;
    }
};
## 总结体会：
使用反转函数reverse反转，然后返回即可。