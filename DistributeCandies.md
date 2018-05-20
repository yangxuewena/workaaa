# Practice
分糖果
## 问题
#### 
给定一个偶数长度的数组，其中不同的数字代表着不同种类的糖果，每一个数字代表一个糖果。你需要把这些糖果平均分给一个弟弟和一个妹妹。返回妹妹可以获得的最大糖果的种类数。
## 编程实现：
class Solution {
public:

    int distributeCandies(vector<int>& candies)
    {
        int count=1;
        int i=candies.size()/2;
        sort(candies.begin(),candies.end());
        for(int j=1;j<candies.size();j++)
        {
            if(candies[j]!=candies[j-1])
            {
                count++;
            }
        }
        if(count>=i)
        {
            return i;
        }
        else
        {
           return count;
        }
    }
};
## 总结体会：
对数组candies进行排序，遍历数组，找出不重复元素的个数，若该数小于糖果总数的一半，返回该数；若该数大于糖果总数的一半，返回糖果总数的一半。