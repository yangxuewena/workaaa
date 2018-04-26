# Practice
 两数之和
## 问题分析：
#### 
给定一个整数数组和一个目标值，找出数组中和为目标值的两个数。

你可以假设每个输入只对应一种答案，且同样的元素不能被重复利用。
## 编程实现：
```C
/**
 * Note: The returned array must be malloced, assume caller calls free().
 */
int* twoSum(int* nums, int numsSize, int target)
{
   int *a=(int*)malloc(2*sizeof(int));
    for(int i=0;i<numsSize-1;i++)
    {
        for(int j=i+1;j<numsSize;j++)
        {
            if (nums[i]+nums[j]==target)
            {
                a[0]=i;
                a[1]=j;
            }
        } 
    }  
    return a;
}
```
## 总结体会：
本题遍历数组，i从第一个数开始，j从i+1开始找出数组中和为目标值的两个数。
