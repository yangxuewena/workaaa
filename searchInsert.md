# Practice
搜索插入位置
## 问题
#### 
给定一个排序数组和一个目标值，在数组中找到目标值，并返回其索引。如果目标值不存在于数组中，返回它将会被按顺序插入的位置。
你可以假设数组中无重复元素
## 编程实现：
class Solution {
public:

    int searchInsert(vector<int>& nums, int target) 
    {
        for(int i=0;i<nums.size();i++)
        {
            if(nums[i]==target)
            {
                return i;
            }
        }
        for(int i=0;i<nums.size();i++)
        {
            if(nums[i]<target && nums[i+1]>target)
            {
                return i+1;
            }
            else if(nums[0]>target)
            {
                return 0;
            }
            else if(nums[nums.size()-1]<target)
                return nums.size();
        }
        
    }
};
## 总结体会：
先遍历一遍nums ，看是否存在与target相等的元素，若有，直接返回下标；若没有则进入第二个for循环，看target是否在数组区间内，若小于最小元素返回0；若大于最大元素返回nums.size();在数组区间内返回按顺序插入的位置。