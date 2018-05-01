# Practice
移动零
## 问题
#### 
给定一个数组 nums, 编写一个函数将所有 0 移动到它的末尾，同时保持非零元素的相对顺序。

例如， 定义 nums = [0, 1, 0, 3, 12]，调用函数之后， nums 应为 [1, 3, 12, 0, 0]。
注意事项:

必须在原数组上操作，不要为一个新数组分配额外空间。
尽量减少操作总数
## 编程实现：

class Solution {

public:

    void moveZeroes(vector<int>& nums) {
        int j=0;
        for(int i=0;i<nums.size();i++)
        {
            if(nums[i]!=0)
            {
                nums[j]=nums[i];
                j++;
            }   
        }
        for(int i=j;i<nums.size();i++)
            nums[i]=0;
    }
};

## 总结体会：
定义一个变量，遍历数组每个元素，若不为零变量数值加一，剩余位置用零补齐。