# Practice
求众数
## 问题
#### 
给定一个大小为 n 的数组，找到其中的众数。众数是指在数组中出现次数大于 ⌊ n/2 ⌋ 的元素。

你可以假设数组是非空的，并且给定的数组总是存在众数。
## 编程实现：
class Solution {
public:

    int majorityElement(vector<int>& nums)
    {
        int i;
        int count=1;
        int an=nums.size()/2;
        sort(nums.begin(),nums.end());
        for(i=1;i<nums.size();i++)
        {
            if(nums[i]==nums[i-1])
            {
                count++;
            }
            else
            {
                if(count>an)
                {
                   break;
                }
            }
        }
        return nums[i-1];
    }
};
## 总结体会：
对数组进行排序，然后遍历数组，计数相同的个数，若大于数组长度一般则返回。