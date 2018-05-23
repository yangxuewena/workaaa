# Practice
 只出现一次的数字 II
## 问题分析：
#### 
给定一个非空整数数组，除了某个元素只出现一次以外，其余每个元素均出现了三次。找出那个只出现了一次的元素
## 编程实现：
class Solution {
public:

    int singleNumber(vector<int>& nums) 
    {
        sort(nums.begin(),nums.end());
        if(nums[0]!=nums[1])
            return nums[0];
        if(nums[nums.size()-2]!=nums[nums.size()-1])
            return nums[nums.size()-1];
        for(int i=1;i<nums.size()-1;i++)
        {
            if(nums[i]!=nums[i-1] && nums[i]!=nums[i+1])
                return nums[i];
        }
        
    }
};
## 总结体会：
首先判断第一个和最后一个数字是否只出现一次，若是，则返回；若不是，遍历第二个至倒数第二个数字，判断该数与其前面和后面数字是否相等，若都不相等，则返回。
