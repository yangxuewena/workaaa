# Practice
最大连续1的个数
## 问题分析：
#### 
给定一个二进制数组， 计算其中最大连续1的个数。
## 编程实现：
class Solution
 {
public:
   
 int findMaxConsecutiveOnes(vector<int>& nums) 

{

	int res = 0, cnt = 0;
	for (int num : nums)
    {              
        cnt = (num == 0) ? 0 : cnt + 1;
        res = max(res, cnt);
    }
    return res;    
    }
};
## 总结体会：
该题遍历一遍数组，用cnt来记录1的个数，num=0，cnt置0，否则cnt加1，然后每次更新res。