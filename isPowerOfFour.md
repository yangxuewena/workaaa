# Practice
4的幂
## 问题
#### 
给定一个整数 (32位有符整数型)，请写出一个函数来检验它是否是4的幂。
## 编程实现：
class Solution {
public:

    bool isPowerOfFour(int num)    {
        while(num>1)
        {
            if(num%4!=0)
            {
                return false;
            }
            else
            {
                num=num/4;
            }
        }
        if(num==1)
        {
            return true;
        }
        else
        {
            return false;
        }
    }
};

## 总结体会：
先判断该数是否能被4整除，不能不是4的幂，若可以则将该数除4，一直循环判断，num小于等于1时跳出循环，再判断是否等于1，等于1返回true，小于1返回false。