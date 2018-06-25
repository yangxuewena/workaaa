# Practice
排列硬币
## 问题
#### 
你总共有 n 枚硬币，你需要将它们摆成一个阶梯形状，第 k 行就必须正好有 k 枚硬币。
给定一个数字 n，找出可形成完整阶梯行的总行数。
n 是一个非负整数，并且在32位有符号整型的范围内。
## 编程实现：
class Solution {
public:

    int arrangeCoins(int n) 
    {
        if(n==0) return 0;
        else
        {
           int cur=1,retain=n-1;
            while(cur+1<=retain)
            {
                ++cur;
                retain-=cur;
            }
            return cur;
        }
    }
};
## 总结体会：
如果硬币个数为0时总行数为0，即返回0；若硬币总个数不为0，用while循环找可形成完整阶梯行的总行数。