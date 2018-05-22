# Practice
两数之和 II - 输入有序数组
## 问题
#### 
给定一个已按照升序排列 的有序数组，找到两个数使得它们相加之和等于目标数。

函数应该返回这两个下标值 index1 和 index2，其中 index1 必须小于 index2。


## 编程实现：

class Solution {
public:

    vector<int> twoSum(vector<int>& numbers, int target) 
    {
        int l=0;
        int r=numbers.size()-1;
        while(l<r)
        {
            if(numbers[l]+numbers[r]==target)
            {
                return {l+1,r+1};
            }
            else if(numbers[l]+numbers[r]>target)
            {
                r--;
            }
            else
            {
                l++;
            }
        }
        return {};
    }
};
## 总结体会：
将数组第一个和最后一个相加，若等于target，直接返回；若小于target，l右移一个；若大于target，r左移一个。