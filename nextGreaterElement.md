# Practice
下一个更大元素 I
## 问题
#### 
给定两个没有重复元素的数组 nums1 和 nums2 ，其中nums1 是 nums2 的子集。找到 nums1 中每个元素在 nums2 中的下一个比其大的值。

nums1 中数字 x 的下一个更大元素是指 x 在 nums2 中对应位置的右边的第一个比 x 大的元素。如果不存在，对应位置输出-1。
## 编程实现：
class Solution {
public:

    vector<int> nextGreaterElement(vector<int>& findNums, vector<int>& nums) 
    {
        int k;
        int j;
        vector<int>ans; 
        for(int i=0;i<findNums.size();i++)
        {
            for(j=0;j<nums.size();j++)
            {
                if(findNums[i]==nums[j])
                {
                    break;
                }
            }
            for(k=j+1;k<nums.size();k++)
            {
                if(nums[k]>findNums[i])
                {
                    ans.push_back(nums[k]); 
                    break;
                }
            }
          if(k==nums.size()) ans.push_back(-1);
        }
        return ans;
    }
};
## 总结体会：
先遍历数组nums，找到数组findnums中元素x在数组nums中的位置j，然后从j+1个位置开始判断，如果大于x就存起来，找不到存入-1，返回。