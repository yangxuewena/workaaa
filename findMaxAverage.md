# Practice
子数组最大平均数 I
## 问题
#### 
给定 n 个整数，找出平均数最大且长度为 k 的连续子数组，并输出该最大平均数。
## 编程实现：
class Solution {
public:

    double findMaxAverage(vector<int>& nums, int k) 
    {
        int sum=0;
        int maxsum;
        for(int i=0;i<k;i++)
        {
            sum=sum+nums[i];
        }
        maxsum=sum;
        for(int l=0 , r=k ; r<nums.size() ; l++,r++)
        {
            sum=sum+nums[r]-nums[l];
            if(sum>maxsum)
            {
                maxsum=sum;
            }
        }
        return (double)maxsum/k;
    }
};
## 总结体会：
先算出前k个元素的sum，之后依次向右移动，每次删掉最左边的元素，加上最右边的元素，并在每次移动时，更新maxSum。当枚举结束后，返回 maxSum / k。