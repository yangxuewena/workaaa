# Practice
字符的最短距离
## 问题
#### 
给定一个字符串S，和一个字符C。求出S中每个字符到最近的字符C的距离。
## 编程实现：
class Solution {
public:

    vector<int> shortestToChar(string S, char C) {
        vector<int> res(S.size(),0);
        vector<int> flag;
        for(int i=0;i<S.size();i++)
            if(S[i]==C)
                flag.push_back(i);

        for(int i =0;i<S.size();i++){
            if(S[i]!=C){
                int mind = S.size();
                for(int j = 0;j<flag.size();j++)
                    mind = mind<abs(flag[j]-i)?mind:abs(flag[j]-i);
                res[i]=mind;
            }
        }
        return res;
    }
};
## 总结体会：
首先建立一个数组flag将S中所有C存在的位置保存下来。然后遍历S字符串，将其与C中保存的位置依次求距离(差的绝对值)，然后保存下来最短距离就可以。