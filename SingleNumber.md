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
对非空整数数组进行排序，先判断第一个数和最后一个数是否只出现一次，出现一次即返回，然后遍历第二个至倒数第二个，若某一个数与前面后面元素均不重复，则返回该数