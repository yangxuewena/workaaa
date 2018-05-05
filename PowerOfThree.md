# Practice
3的幂
## 问题
#### 
给出一个整数，写一个函数来确定这个数是不是3的一个幂。
## 编程实现：
class Solution {
public:

    bool isPowerOfThree(int n) 
    {
        if(n<=0) return false;
        if(n==1) return true;
        while(n>0 && n%3==0)
        {
            n=n/3;
            if(n==1) return true;
        }
        return false;
    }
};
## 总结体会：
将这个数除以3，如果整除则继续除，最后等于1则为3的幂，否则不是。