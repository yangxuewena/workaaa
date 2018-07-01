# Practice
三个数的最大乘积
## 问题
#### 
给定一个整型数组，在数组中找出由三个数组成的最大乘积，并输出这个乘积。
## 编程实现：
class Solution {
public:

    int maximumProduct(vector<int>& nums) 
    {
        int max1;
        int max2;
        int len=nums.size();
        sort(nums.begin(),nums.end());
        max1=nums[len-1]*nums[len-2]*nums[len-3];
        max2=nums[0]*nums[1]*nums[len-1];
        if(max1>max2) return max1;
        else return max2;
        
    }
};
## 总结体会：
三个数乘积最大只能有两种情况，一种是三个最大正数直接乘起来最大，另一种就是两个最小的负数乘起来再乘以一个最大的正数。先对数组进行排序，载分别算出两种情况，然后比较返回最大的。