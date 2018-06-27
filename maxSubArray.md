# Practice
最大子序和
## 问题
#### 
给定一个整数数组 nums ，找到一个具有最大和的连续子数组（子数组最少包含一个元素），返回其最大和。 
## 编程实现：
class Solution {
public:

    int maxSubArray(vector<int>& nums) 
    {
        int max=nums[0];
        for(int i=0;i<nums.size();i++)
        {
            if(max<nums[i])
            max=nums[i];
        }
        if(max<0)return max;
        int sum=0;
        max=0;
        for(int i=0;i<nums.size();i++)
        {
            sum+=nums[i];
            if(sum<0)sum=0;
            if(sum>max)
            max=sum;
        }
        return max;
    }
};
## 总结体会：
求最大值，如果数组中元素都小于0,则直接返回数组的最大值。对于一般的情况,遍历求数组，同时对其求和，如果和数变得小于0，那就说明了此时这个子数组是不符合题意的，如果和数为正且大于之前求和过程中记录的最大值，那就将这个和数赋值给max，这样遍历一趟就将其中的最大和给求出来了。