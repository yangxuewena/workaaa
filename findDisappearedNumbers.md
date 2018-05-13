# Practice
找到所有数组中消失的数字
## 问题
#### 
给定一个范围在  1 ≤ a[i] ≤ n ( n = 数组大小 ) 的 整型数组，数组中的元素一些出现了两次，另一些只出现一次。

找到所有在 [1, n] 范围之间没有出现在数组中的数字。
## 编程实现：
class Solution {
public:

    vector<int> findDisappearedNumbers(vector<int>& nums)
    {
       vector<int>ans;  
        int i = 0;       
        while(i < nums.size())
        {  
            if(nums[i] != nums[nums[i]-1])  
                swap(nums[i], nums[nums[i]-1]);  
            else  
                i++;  
        }  
        for(int i = 0; i < nums.size(); i++){  
            if(nums[i] != i+1)  
                ans.push_back(i+1);  
        }  
        return ans; 
    }
};
## 总结体会：
把每个元素都放在下标对应的位置，然后遍历数组，找出不对应的地方输出即可。