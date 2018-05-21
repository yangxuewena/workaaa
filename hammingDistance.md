# Practice
汉明距离
## 问题
#### 
两个整数之间的汉明距离指的是这两个数字对应二进制位不同的位置的数目。

给出两个整数 x 和 y，计算它们之间的汉明距离。
## 编程实现：
class Solution {
public:

    int hammingDistance(int x, int y) 
    {
         unsigned int num = x^y;
         int count=0;
          while(num)
          {    
              if(num%2==1)
              {
                  count++;
              }
              num=num<<1;
          }  
        return count;
    }
};
## 总结体会：
对两个数进行异或，得到一个不同位置为1的整数，该整数不断右移，一直判断最低位是否为1，若为1，count加1。