# Practice
至少是其他数字两倍的最大数
## 问题
#### 
在一个给定的数组nums中，总是存在一个最大元素 。

查找数组中的最大元素是否至少是数组中每个其他数字的两倍。

如果是，则返回最大元素的索引，否则返回-1。
## 编程实现：
class Solution {
public:

    int dominantIndex(vector<int>& nums) 
    {
        vector<int> ans;
        for(int i=0;i<nums.size();i++)
        {
            ans.push_back(nums[i]);
        }
        sort(nums.begin(),nums.end());
        if(nums[nums.size()-1]>=2*nums[nums.size()-2])
        {
            for(int j=0;j<nums.size();j++)
            {
                if(ans[j]==nums[nums.size()-1])
                {
                    return j;
                }
            }
        }
        else
        {
            return -1;
        }
        
    }
};
## 总结体会：
先将数组复制到ans，然后对数组nums排序，判断最后一位是否至少是倒数第二位的两倍，若不是直接返回-1；若是，则返回数组ans中与nums最后一位所相同的数的索引即可。