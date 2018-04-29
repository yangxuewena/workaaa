# Practice
有效的完全平方数
## 问题
#### 
给定一个正整数 num，编写一个函数，如果 num 是一个完全平方数，则返回 True，否则返回 False。
## 编程实现：
class Solution {
public:

    bool isPerfectSquare(int num)
    {
         int i = 1;  
         while (num > 0)
         {  
	         num = num - i;  
	         i = i + 2;  
     	 }  
     	return num == 0;
    }
};
## 总结体会：
n的平方等于从1开始的n个连续的奇数的和，然后用循环判断，并返回。