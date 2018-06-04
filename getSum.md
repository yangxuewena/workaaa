# Practice
两整数之和
## 问题
#### 
不使用运算符 + 和-，计算两整数a 、b之和。
## 编程实现：
class Solution {
public:

    int getSum(int a, int b) {
        while(b!=0)
        {
            if(b<0)
            {
                a--;
                b++;
            }
            else
            {
                a++;
                b--;
            }
        }
        return a;
    }
};
## 总结体会：
利用自加与自减运算符实现。