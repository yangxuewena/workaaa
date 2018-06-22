# Practice
各位相加
## 问题
#### 
给定一个正整数 n ，输出报数序列的第 n 项。
报数序列是指一个整数序列，按照其中的整数的顺序进行报数，得到下一个数。
1 被读作  "one 1"  ("一个一") , 即 11。
11 被读作 "two 1s" ("两个一"）, 即 21。
21 被读作 "one 2",  "one 1" （"一个二" ,  "一个一") , 即 1211。
## 编程实现：
class Solution {
public:

    string countAndSay(int n)
    {
         if (n <= 0) return "";
         string res = "1";
         while (--n)
         {
              string cur = "";
              for (int i = 0; i < res.size(); ++i) {
              int cnt = 1;
              while (i + 1 < res.size() && res[i] == res[i + 1])
              {
                     ++cnt;
                     ++i;
              }
                 cur += to_string(cnt) + res[i];
              }
              res = cur;
         }
         return res;  
    }
};
## 总结体会：
分析这个数组的规律，第i+1个字符串是第i个字符串的读法，算法就是对于前一个数，找出相同元素的个数，把个数和该元素存到新的string里。

