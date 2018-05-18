# Practice
丑数
## 问题
#### 
编写一个程序判断给定的数是否为丑数。

丑数就是只包含质因数 2, 3, 5 的正整数。
## 编程实现：
class Solution {
public:

    bool isUgly(int num) 
    {
        if(num<=0) return false;
        if(num==1) return true;
        while(num>1)
        {
            if(num%2==0)
            {
                num=num/2;
            }
            else if(num%3==0)
            {
                num=num/3;
            }
            else if(num%5==0)
            {
                num=num/5;
            }
            else
                return  false;
        }
         return true;  
    }
};
## 总结体会：
若一个数小于等于零，不是丑数，等于一是丑数，若大于1，判断它是否只能被2,3,5整除，若只能被2,3,5整除则是丑数，否则不是。