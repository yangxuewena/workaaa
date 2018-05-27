# Practice
两个数组的交集 II
## 问题
#### 
给定两个数组，写一个方法来计算它们的交集。
## 编程实现：
class Solution {
public:

    vector<int> intersect(vector<int>& nums1, vector<int>& nums2) 
    {
        vector<int> inter;
        sort(nums1.begin(),nums1.end());
        sort(nums2.begin(),nums2.end());
        int i=0;
        int j=0;
        while(i<nums1.size() &&j<nums2.size())
        {
            if(nums1[i]==nums2[j])
            {
                inter.push_back(nums1[i]);
                i++;
                j++;
            }
            else if(nums1[i]>nums2[j])
            {
                j++;
            }
            else
            {
                i++;
            }
        }
        return inter;
    }
};
## 总结体会：
先对两个数组进行排序，然后从两个数组的第一个数开始比较，若相等就存入；若nums1[i]大于nums2[j],j加1；若nums1[i]小于nums2[j]，i加1。