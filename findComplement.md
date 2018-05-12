# Practice
数字的补数
## 问题
#### 
给定一个正整数，输出它的补数。补数是对该数的二进制表示取反。


## 编程实现：
class Solution {
public:

    int findComplement(int num) 
    {
        if(num==0) return 1;
        int res;
        int com=0;
        int con=1;
        while(num!=0)
        {
            if (num % 2 == 1)  
            {  
                res = 0;  
            }  
            else  
            {  
                res = 1;  
            }  
            com=com+res*con;  
            con*=2;
            num=num/2;
        }
        return com;
    }
};
## 总结体会：
若该数为0，返回1，不为0时，不断取余，若余数为0，用1乘这个数的权值，余数为1，用0乘这个数的权值。