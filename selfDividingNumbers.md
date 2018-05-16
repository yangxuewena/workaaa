# Practice
自除数
## 问题
#### 
自除数 是指可以被它包含的每一位数除尽的数。

例如，128 是一个自除数，因为 128 % 1 == 0，128 % 2 == 0，128 % 8 == 0。

还有，自除数不允许包含 0 。

给定上边界和下边界数字，输出一个列表，列表的元素是边界（含边界）内所有的自除数。
## 编程实现：
class Solution {
public:

    vector<int> selfDividingNumbers(int left, int right) 
    {
        vector<int> ans;
        int j;
        int an;
        for(int i=left;i<=right;i++)
        {
            an=i;
            while(i)
            {
                j=an % 10;
                if(j==0) break;
                else if(i%j!=0) break;
                else an=an/10;
            }
            if(an==0)
            {
                ans.push_back(i);
            }
        }
        
        return ans;
    }
};
## 总结体会：
从left到right逐一判断i，先取余，判断是否为零，若为零，跳出while循环，再判断i对该位取余是否为零，最后用an是否等于零判断i是否是自除数，若是，则存入ans，最后返回ans。