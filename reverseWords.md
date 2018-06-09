# Practice
反转字符串中的单词 III
## 问题
#### 
给定一个字符串，你需要反转字符串中每个单词的字符顺序，同时仍保留空格和单词的初始顺序。
## 编程实现：
class Solution {
public:

    string reverseWords(string s)
    {
        string ans="";
        vector<string>str;
         string st = "";
         for(int i = 0; i < s.length(); i++) {
             if(s[i] != ' ')
                 st += s[i];
             
             if(s[i] == ' '|| i == s.length()-1) {
                 str.push_back(st);
                 st = "";
                 
             }
             
         }
         for(int i = 0; i < str.size(); i++) {
             for(int j = str[i].length() - 1; j >= 0; j--) {
                 ans += str[i][j];
             }
             if(i !=  str.size()-1) {
                 ans += " ";
             }
         }
         return ans;
        
    }
};
## 总结体会：
先将给定的字符串s中的单词拆分出来str，然后单个处理每个单词，拼接成一个新的字符串ans，返回ans.