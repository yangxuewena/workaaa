# Practice
 Given an integer, write a function to determine if it is a power of two.
给定一个数，判断它是否是2的幂。
## 问题分析：
#### 
该数除以2
## 编程实现：
class Solution {
public:
    bool isPowerOfTwo(int n) {
        int num=n;     
        while(num>0 && num%2==0)  //整除
            num/=2;  
        return num==1;
        
    }
};
## 总结体会：
将这个数除以2，如果整除则继续除，最后等于1则为2的幂，否则不是。
