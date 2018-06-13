# Practice
二进制求和
## 问题
#### 
给定两个二进制字符串，返回他们的和（用二进制表示）。

输入为非空字符串且只包含数字 1 和 0。
## 编程实现：
class Solution {
public:

    string addBinary(string a, string b) 
    {
        string res;
         int na = a.size();
         int nb = b.size();
         int n = max(na, nb);
         bool carry = false;
          if (na > nb)
         {
            for (int i = 0; i < na - nb; ++i) b.insert(b.begin(), '0');
         }
        else if (na < nb) 
        {
             for (int i = 0; i < nb - na; ++i) a.insert(a.begin(), '0');
        }
         for (int i = n - 1; i >= 0; --i) 
		{
             int tmp = 0;
             if (carry) tmp = (a[i] - '0') + (b[i] - '0') + 1;
           else tmp = (a[i] - '0') + (b[i] - '0');
             if (tmp == 0) 
			{
                 res.insert(res.begin(), '0');
                 carry = false;
            }
             else if (tmp == 1) 
			{
                 res.insert(res.begin(), '1');
                 carry = false;
             }
             else if (tmp == 2)
			{
                res.insert(res.begin(), '0');
                 carry = true;
             }
             else if (tmp == 3）
			 {
                 res.insert(res.begin(), '1');
                 carry = true;
             }
         }
         if (carry) res.insert(res.begin(), '1');
         return res; 
    }
};
## 总结体会：
二进制数相加，保存在string中，将string和int之间互相转换，并且每位相加时，会有进位的可能，会影响之后相加的结果。而且两个输入string的长度也可能会不同。这时我们需要新建一个string，它的长度是两个输入string中较大的那个，并且要把较短的那个输入string通过在开头加字符‘0’来补充为和较大的那个一样的长度。逐个从两个string的末尾开始取出字符，然后转为数字，相加，如果大于等于2，则标记进位标志carry，并且给新string加入一个字符‘0’