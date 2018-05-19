# Practice
数组拆分1
## 问题
#### 
给定长度为 2n 的数组, 你的任务是将这些数分成 n 对, 例如 (a1, b1), (a2, b2), ..., (an, bn) ，使得从1 到 n 的 min(ai, bi) 总和最大。
## 编程实现：
class Solution {
public:

    int arrayPairSum(vector<int>& nums)
    {
        int an=0;
        sort(nums.begin(),nums.end());
        for(int i=0;i<nums.size();i=i+2)
        {
            an=an+nums[i];
        }
        return an;
    }
};
## 总结体会：
先对数组排序，然后取出下标为偶数的数字相加返回即可。