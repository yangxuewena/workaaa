# Practice
各位相加
## 问题
#### 
给一个非负整数 num，反复添加所有的数字，直到结果只有一个数字。
## 编程实现：
class Solution {
public:

    int addDigits(int num) 
    {
        int sum =0;
        while(1)
        {
            while(num)
            {
                sum=sum+num%10;
                num=num/10;
            }
            if(sum<10)
                break;
            num=sum;
            sum=0;
        }
      return sum; 
    }
};
## 总结体会：
调用两重循环，先对num取余相加得到各位的和sum，若和sum小于10，跳出循环，返回sum，若和sum大于10，继续循环，将sum赋值给num，重复执行，最后返回一个小于10的sum。