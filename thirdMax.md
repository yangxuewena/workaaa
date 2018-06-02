# Practice
第三大的数
## 问题
#### 
给定一个非空数组，返回此数组中第三大的数。如果不存在，则返回数组中最大的数。要求算法时间复杂度必须是O(n)。
## 编程实现：
class Solution {
public:

    int thirdMax(vector<int>& nums)
    {
        sort(nums.begin(),nums.end());
        nums.erase(unique(nums.begin(),nums.end()),nums.end());  
        if(nums.size()<3)
        {
            return nums[nums.size()-1];
        }
        else
        {
            return nums[nums.size()-3];
        }
    }
};
## 总结体会：
将数组排序删除重复元素，后判断数组个数是否大于等于3，若不大于等于3，返回最后一个数；若大于等于3，返回倒数第三个数。