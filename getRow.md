# Practice
杨辉三角II
## 问题
#### 
给定一个非负索引 k，其中 k ≤ 33，返回杨辉三角的第 k 行。
## 编程实现：
class Solution {
public:

    vector<int> getRow(int rowIndex)
    {
       if(rowIndex == 0)
	   {
            return vector<int>{1};
       }
       if(rowIndex == 1)
	   {
            return vector<int>{1,1};
       }
        vector<int> prev = getRow(--rowIndex);
        vector<int> temp;
        temp.push_back(1);
        for(int i = 0; i < prev.size()-1; i++)
		{
            temp.push_back(prev[i]+prev[i+1]);
        }
        temp.push_back(1);
        return temp;
    }
};
## 总结体会：
这是一个递归问题，要求取第n行，就要先求第n-1行,采用在函数内部调用函数自身的方式。首先若rowindex为0，返回1；若rowindex为1，返回1,1；其余情况，先在temp存入1，然后将其前一层的数依次相加存入，再存入1，前一层的数相加调用函数自身。