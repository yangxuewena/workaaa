# Practice
字符串中的第一个唯一的字符
## 问题
#### 
给定一个字符串，找到它的第一个不重复的字符，并返回它的索引。如果不存在，则返回 -1。
## 编程实现：
class Solution {
public:

    int firstUniqChar(string s)
    {
       
        map<char,int> m1;
        for(int i=0;i<s.length(); i++){
            m1[s[i]] ++;
        }
        for(int i=0;i<s.length(); i++){
            if(m1[s[i]]==1 )
                return i;
        }
        return -1;
        
    }
};
## 总结体会：
定义map映射遍历，记录所有字母出现次数，再遍历输出只出现一次的字符，若没有找到，返回-1。