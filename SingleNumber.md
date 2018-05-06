# Practice
只出现一次的数字
## 问题
#### 
给定一个非空整数数组，除了某个元素只出现一次以外，其余每个元素均出现两次。找出那个只出现了一次的元素。
## 编程实现：
class Solution {
public:

    int singleNumber(vector<int>& nums) {
        sort(nums.begin(),nums.end());
        if(nums[0]!=nums[1]) 
            return nums[0];
        if(nums[nums.size()-2]!=nums[nums.size()-1]) 
            return nums[nums.size()-1];
        int i;
        for( i=1;i<nums.size()-1;i++)
        {
            if  ( (nums[i]!=nums[i-1]) && ( nums[i]!=nums[i+1]) ) 
                break;
        }
        return nums[i];
    }
};
## 总结体会：
将非空数组排序，先判断第一个数和最后一个数是否只出现一次，若是则返回，若不是，遍历数组中第2个至倒数第2个，若某一个数与它前面和后面均不重复则返回。