# Practice
判断路线成圈
## 问题
#### 
初始位置 (0, 0) 处有一个机器人。给出它的一系列动作，判断这个机器人的移动路线是否形成一个圆圈，换言之就是判断它是否会移回到原来的位置。

移动顺序由一个字符串表示。每一个动作都是由一个字符来表示的。机器人有效的动作有 R（右），L（左），U（上）和 D（下）。输出应为 true 或 false，表示机器人移动路线是否成圈。
## 编程实现：
class Solution {
public:

    bool judgeCircle(string moves) 
    {
        int l=0;
        int r=0;
        int u=0;
        int d=0;
        for(int i=0;i<moves.length();i++)
        {
            if(moves[i]=='L')
            {
                l++;
            }
            if(moves[i]=='R')
            {
                r++;
            }
            if(moves[i]=='U')
            {
                u++;
            }
            if(moves[i]=='D')
            {
                d++;
            }
        }
        if(l==r && u==d)
        {
            return true; 
        }
        else
            return false;
        
    }
};
## 总结体会：
遍历字符串，计数'L''R''U''D'的个数，若L与R，U与D个数相等，则移动路线成圈。