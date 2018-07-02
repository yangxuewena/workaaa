# Practice
分发饼干
## 问题
#### 
假设你是一位很棒的家长，想要给你的孩子们一些小饼干。但是，每个孩子最多只能给一块饼干。对每个孩子 i ，都有一个胃口值 gi ，这是能让孩子们满足胃口的饼干的最小尺寸；并且每块饼干 j ，都有一个尺寸 sj 。如果 sj >= gi ，我们可以将这个饼干 j 分配给孩子 i ，这个孩子会得到满足。你的目标是尽可能满足越多数量的孩子，并输出这个最大数值。
可以假设胃口值为正。
一个小朋友最多只能拥有一块饼干。
## 编程实现：
class Solution {
public:

    int findContentChildren(vector<int>& g, vector<int>& s)
    {
        int nums=0;
        sort(g.begin(),g.end());
        sort(s.begin(),s.end());
        for (int i = 0,j = 0; i < g.size() && j < s.size(); ) 
        {
            if(g[i]<=s[j])
            {
                nums++;
                i++;
                j++;
            }
            else
                j++;
        }
        return nums;
    }
};
## 总结体会：
先将两个数组从小到大排列，然后挨个比较大小，当饼干的大小大于某个孩子的胃口时，nums++，判断下一个饼干和孩子。