# Practice
位1的个数
## 问题
#### 
编写一个函数，输入是一个无符号整数，返回其二进制表达式中数字位数为 ‘1’ 的个数（也被称为汉明重量）。
## 编程实现：
class Solution 
{
public:

    int hammingWeight(uint32_t n)
    {
         int count = 0;
         while(n != 0)
         {
            if(n&1 == 1)
            {
                ++count;
            }
            n = n >> 1;
        }
        return count;
    }
};
## 总结体会：
运用移位运算符, 将输入每一位与1相与，与之后判断是否为1，若为1则count加1。