# Practice
移除元素
## 问题
#### 
给定一个数组 nums 和一个值 val，你需要原地移除所有数值等于 val 的元素，返回移除后数组的新长度。

不要使用额外的数组空间，你必须在原地修改输入数组并在使用 O(1) 额外空间的条件下完成。

元素的顺序可以改变。你不需要考虑数组中超出新长度后面的元素。。
## 编程实现：
class Solution {
public:

    int removeElement(vector<int>& nums, int val)
    {
         int j=0;
        for(int i=0;i<nums.size();i++)
        {
            if(nums[i]!=val)
            {
                nums[j]=nums[i];
                j++;
            }
        }
        return j;    
    }
};
## 总结体会：
遍历数组，若某数不等于val，将其赋值给nums[j],同时j加1，最后返回j。