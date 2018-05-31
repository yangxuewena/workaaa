# Practice
回文数
## 问题
#### 
判断一个整数是否是回文数。回文数是指正序（从左向右）和倒序（从右向左）读都是一样的整数。
## 编程实现：
class Solution {
public:

    bool isPalindrome(int x) {
    if (x < 0)  
    {  
        return false;  
    }  
  
    int l = 1;  
    while (x/l > 9)  
    {  
        l *= 10;  
    }  
      
    int r = 1;  
    while (l > r)  
    {  
        if (((x/l)%10) != ((x/r)%10))  
        {  
            return false;  
        }  
        l /= 10;  
        r *= 10;  
    }  
  
    return true;   
    }
};
## 总结体会：
若该数小于0，不是回文数，大于0小于10是回文数，若大于9则取出最高位与最低位比较是否相等，若相等再次高位与次低位，依次循环，若有一组不相等就不是回文数。