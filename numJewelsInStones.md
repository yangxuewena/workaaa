# Practice
宝石与石头
## 问题
#### 
给定字符串J 代表石头中宝石的类型，和字符串 S代表你拥有的石头。 S 中每个字符代表了一种你拥有的石头的类型，你想知道你拥有的石头中有多少是宝石。
## 编程实现：
class Solution {
public:

    int numJewelsInStones(string J, string S) 
    {
        int num=0;
        for(int i=0;i<J.length();i++)
        {
            for(int j=0;j<S.length();j++)
            {
                if(J[i]==S[j])
                {
                    num++;
                }
            }
        }
        return num;
    }
};
## 总结体会：
调用双重循环，遍历两个字符串，若存在相同元素，num加1，完成后返回num即可。