# Practice
删除排序数组中的重复项
## 问题
#### 
给定一个排序数组，你需要在原地删除重复出现的元素，使得每个元素只出现一次，返回移除后数组的新长度。
## 编程实现：
class Solution {
public:

    int removeDuplicates(vector<int>& nums) 
    {
        int n=nums.size();
        if(n==0) return 0;
        int i = 1;  
        int j = 1;  
        while(i < n)
        {  
             if(nums[i] > nums[i-1])
             {
                nums[j] = nums[i];
                 j++;
             }
                 i++;         
        }  
        return j;  
    }
};
## 总结体会：
若nums中没有数，返回0；有一个数返回1；若nums中数的个数大于1，从第二个数依次判断该数是否大于前一个数，若大于j加一。