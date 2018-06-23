# Practice
有效的字母异位词
## 问题
#### 
给定两个字符串 s 和 t ，编写一个函数来判断 t 是否是 s 的一个字母异位词。
## 编程实现：
class Solution {
public:

    bool isAnagram(string s, string t) 
    {
        int sn[26]={0};
        int tn[26]={0};
        for(int i=0;i<s.size();i++)
        {
            sn[s[i]-'a']++;
        }
        for(int i=0;i<t.size();i++)
        {
            tn[t[i]-'a']++;
        }
        for(int i=0;i<26;i++)
        {
            if(sn[i]!=tn[i])
                return false;
        }
        return true;
    }
};
## 总结体会：
调用for函数统计两个字符串中26个小写字母个数，然后比较两个字符串中各个小写字母的个数是否相等，如果相同返回true，不相等返回false。