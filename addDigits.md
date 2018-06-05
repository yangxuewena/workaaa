# Practice
第N位数
## 问题
#### 
在无限的整数序列 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, ...中找到第 n 个数字。
## 编程实现：
class Solution {
public:

    int findNthDigit(int n)
    {
        long base = 9,digits = 1;  
        while(n - base * digits > 0)
        {  
            n -= base * digits;  
            base *= 10;  
            digits++;  
        }  
        int index = n % digits;  
        if(index == 0)  
            index = digits;  
        long num = 1;  
        for(int i = 1; i < digits; i++){  
            num *= 10;  
        }  
        num += (index == digits) ? n / digits -1 : n / digits;  
        for(int i = index; i < digits; i++)  
            num /= 10;  
        return num % 10;
    }
};
## 总结体会：
 1-9 有9位数，10-99有180位。首先需要找到这个位数是几位数。 再找到这个数，然后确定这个数的第几位是我们要找的。