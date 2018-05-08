# Practice
两个数组的交集
## 问题
#### 
给定两个数组，写一个函数来计算它们的交集。
## 编程实现：
class Solution {
public:

    vector<int> intersection(vector<int>& nums1, vector<int>& nums2) 
    {
        vector<int>res;
        set<int>res;
        for(int i=0;i<nums1.size();i++)
            for(int j=0;j<nums2.size();j++)
            {
                if(nums1[i]==nums2[j])
                {
                res.push_back(nums1[i]); 
                }
            }
        sort(res.begin(),res.end());
        res.erase(unique(res.begin(),res.end()),res.end());  
        return res;  
    }
};
## 总结体会：
调用双重循环，找出两个数组中重复的元素放到res中，然后对res中元素进行排序，删除重复的元素，返回res。