# Practice
字符串相加
## 问题
#### 
给定两个字符串形式的非负整数 num1 和num2 ，计算它们的和。
num1 和num2 的长度都小于 5100.
num1 和num2 都只包含数字 0-9.
num1 和num2 都不包含任何前导零。
## 编程实现：
class Solution {
public:

    string addStrings(string num1, string num2)
    {
         if(num1.size()<num2.size()) swap(num1, num2);
          for(int i=num2.size(); i<num1.size(); i++) num2 = '0' + num2;
          int carry = 0;
          for(int i=num1.size()-1; i>=0; i--)
          {
              int t = (num2[i]-'0') + (num1[i]-'0') + carry;
              num1[i] = t%10 + '0';
              carry = t/10;
         }
         if(carry==1) num1 = '1' + num1;
         return num1;
    }
};
## 总结体会：
将较短的字符串num2用0补齐，然后逐位相加存到num1中，保存进位，最后返回字符串num即可。