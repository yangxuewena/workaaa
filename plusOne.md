# Practice
加一
## 问题
#### 
给定一个非负整数组成的非空数组，在该数的基础上加一，返回一个新的数组。
最高位数字存放在数组的首位， 数组中每个元素只存储一个数字。
你可以假设除了整数 0 之外，这个整数不会以零开头。
## 编程实现：
class Solution {
public:

    vector<int> plusOne(vector<int>& digits)
    {
        int carry = 1;//设置进位
        int temp = 0;
        for(int i=digits.size()-1 ; i>=0 ; i--)
        {
            temp = digits[i] + carry;
            digits[i] = temp%10;
            carry = temp/10;
        }
        if(carry>0)
        {
            vector<int> result;
            result.push_back(1);
            for(int j = 0 ; j<digits.size() ; j++)
            {
                result.push_back(digits[j]);
            }
            return result;
        }
        return digits;
    }
};
## 总结体会：
可以将carry设置为进位，初始值为1，然后依次记录加一之后每位的变化，遍历完数组之后若carry为1，说明最高位有进位，就将为高位设置为1，再将后面的依次存入，返回即可。