# Practice
猜数字游戏
## 问题
#### 
我们正在玩一个猜数字游戏。 游戏规则如下：
我从 1 到 n 选择一个数字。 你需要猜我选择了哪个数字。
每次你猜错了，我会告诉你这个数字是大了还是小了。
你调用一个预先定义好的接口 guess(int num)，它会返回 3 个可能的结果（-1，1 或 0）：
## 编程实现：
// Forward declaration of guess API.

// @param num, your guess

// @return -1 if my number is lower, 1 if my number is higher, otherwise return 0
int guess(int num);

class Solution {
public:

    int guessNumber(int n) {
        int l=1;
        int r=n;
        int mid=1;
        while(l<r)
        {
            mid=l+(r-l)/2;
            int res=guess(mid);
            if(res==0) return mid;
            else if(res==1) 
                l=mid+1;
            else
                r=mid-1;
        }
        return l;
    }
};
## 总结体会：
利用二分法查找，每次猜中间的数，猜测值过小，就把mid-1赋值给r,猜测值过大就把mid+1赋值给l。