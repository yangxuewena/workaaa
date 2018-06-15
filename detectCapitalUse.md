# Practice
检测大写字母
## 问题
#### 
给定一个单词，你需要判断单词的大写使用是否正确。

我们定义，在以下情况时，单词的大写用法是正确的：

全部字母都是大写，比如"USA"。
单词中所有字母都不是大写，比如"leetcode"。
如果单词不只含有一个字母，只有首字母大写， 比如 "Google"。
否则，我们定义这个单词没有正确使用大写字母。

输入为非空字符串且只包含数字 1 和 0。
## 编程实现：
class Solution {
public:

    bool detectCapitalUse(string word) {
        int cnt=0;
        for(char c:word)
        {
            if(c>='A' && c<='Z')
            {
                ++cnt;
            }
        }
        return cnt==0||cnt==word.size()||(cnt==1&&word[0]<='Z');
    }
};
## 总结体会：
找出所有大写字母的个数captialCount，与字符串长度做比较,都是小写字母、都是大写字母、只有首字母是大写字母的，都返回true。