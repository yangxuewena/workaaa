# Practice
缺失数字
## 问题
#### 
给定一个包含 0, 1, 2, ..., n 中 n 个数的序列，找出 0 .. n 中没有出现在序列中的那个数。
## 编程实现：
class Solution {
public:

    int missingNumber(vector<int>& nums) 
    {
        sort(nums.begin(),nums.end());
        int j=0;
        for(int i=0;i<nums.size();i++)
        {
            if(nums[i]!=j)
            {
                return j;
            }
            j++;
        }
        return j;
    }
};
## 总结体会：
先对数组进行排序，然后遍历数组，找到缺失的数字返回即可。