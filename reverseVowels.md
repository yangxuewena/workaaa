# Practice
反转字符串中的元音字母
## 问题
#### 
编写一个函数，以字符串作为输入，反转该字符串中的元音字母。
## 编程实现：
class Solution {
public:

    string reverseVowels(string s) 
    {
        stack<char> res;
        for(int i = 0 ; i < s.size();i++)
        {
            if(s[i] == 'a'||s[i] == 'e'||s[i] == 'i'||s[i] == 'o'||s[i] == 'u'||s[i] == 'A'||s[i] == 'E'||s[i] == 'I'||s[i] == 'O'||s[i] == 'U')
            {
                res.push(s[i]);
                s[i] = NULL ;
            }            
        }
        for(int i = 0 ; i < s.size();i++)
        {
            if(s[i] == NULL)
            {
                s[i] = res.top() ;
                res.pop();
            }            
        }
        return s ;
    }
};
## 总结体会：
第一次遍历字符串，将所有元音字母入栈，并将该位置填为空，第二次遍历字符串，每次取栈顶元素替换当前元音字母。