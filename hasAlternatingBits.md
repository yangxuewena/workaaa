# Practice
交替位二进制数
## 问题
#### 
给定一个正整数，检查他是否为交替位二进制数：换句话说，就是他的二进制数相邻的两个位数永不相等。
## 编程实现：
class Solution {
public:
    bool hasAlternatingBits(int n)
    {
        bool last = n & 1;
        while (n != 0 && (n & 1) == last) 
        {
            last = 1 - last;
            n >>= 1;
        }
        return n == 0;
        
    }
};

## 总结体会：
每次检查数字二进制的最低位的值后，last取反，将数字向右移位一位，这样每次都只需要检查二进制最低位。
