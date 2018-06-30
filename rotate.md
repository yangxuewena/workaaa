# Practice
旋转数组
## 问题
#### 
给定一个数组，将数组中的元素向右移动 k 个位置，其中 k 是非负数。
## 编程实现：
class Solution {
public:

    void rotate(vector<int>& nums, int k) 
    {
       vector<int>res(nums.size());
        for(int i = 0;i < nums.size() ;++i)
        {
        res[(i+k)%nums.size()] = nums[i];
        }
        nums = res;
    }
};
## 总结体会：
借助中间数组，将nums中下标为i的数字存入res中下标为(i+k)%nums.size()的位置中。再将res赋值给nums。