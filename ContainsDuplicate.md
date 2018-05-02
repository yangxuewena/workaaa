# Practice
存在重复
## 问题
#### 
给定一个整数数组，判断是否存在重复元素。

如果任何值在数组中出现至少两次，函数应该返回 true。如果每个元素都不相同，则返回 false。


## 编程实现：

class Solution {
public:

    bool containsDuplicate(vector<int>& nums) 
    {
       
        if(nums.size()<2) return false;
        sort(nums.begin(),nums.end());
        for(int i=0;i<nums.size()-1;i++)
        {
            if(nums[i]==nums[i+1])
             return true;
        }
        return false;
    }
};
## 总结体会：
考虑先对整数数组进行排序，然后遍历数组，查看相邻数组是否相等。若相等返回true，
无相等的返回false。