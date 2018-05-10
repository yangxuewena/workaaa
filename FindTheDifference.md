# Practice
找不同
## 问题
#### 
给定两个字符串 s 和 t，它们只包含小写字母。

字符串 t 由字符串 s 随机重排，然后在随机位置添加一个字母。

请找出在 t 中被添加的字母。
## 编程实现：
class Solution {
public:

    char findTheDifference(string s, string t)
    {
        sort(s.begin(),s.end());
        sort(t.begin(),t.end());
        int i;
        for( i=0;i<=s.size()-1;i++)
        {
            if(s[i]!=t[i])
                    break;
        }
        return t[i];
    }
};
## 总结体会：
先将两个字符串分别排序，再循环比较排序后字符串中相同位置的字符是否相同，若字符相同，则继续对比下一位若对应位置字符不同，跳出循环，返回t[i];若循环结束都相同，所找的在t的最后，再返回。