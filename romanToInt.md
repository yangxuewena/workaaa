# Practice
罗马数字转整数
## 问题
#### 
给定一个罗马数字，将其转换成整数。输入确保在 1 到 3999 的范围内。
## 编程实现：
class Solution {
public:

    int romanToInt(string s)
    {
        
        map<char, int> A;
        int ans = 0;
        A['I'] = 1, A['V'] = 5, A['X'] = 10, A['L'] = 50, A['C'] = 100, A['D'] = 500, A['M'] = 1000;
        int pre = A[s[0]], now;
        for (int i = 1; i < s.size(); ++i)
            now = A[s[i]], ans += pre * (pre >= now ? 1 : -1), pre = now;
        ans += pre;
        return ans;
    }
};
## 总结体会：
按照罗马数字规则,对每一位：其右边大，减去这个数；其右边小，加上这个数,最后再加上最右边的数