# Practice
Count Primes
计数质数
## 问题分析：
#### 
Count the number of prime numbers less than a non-negative number, n.
求小于一个非负整数n的质数的个数。
## 编程实现：
class Solution
{
public:

    int countPrimes(int n)
    {  
        int count=0;
        if(n==0 || n==1) return 0;
        else if(n==2) return 1;
        else
        {
            for(int i=2;i<n;++i)
            {
                   
                for(int j=2;j<i;++j)
                {
                    if(i%j==0) break;
                }
                if(j==i) count=count+1;
            }
            return count;
        }
    }
    
};
## 总结体会：
调用双重循环，第一重循环遍历小于n的数；第二重循环用来判断i是否为质数，若i%j为0，则不是质数，跳出循环，若i=j，是质数，count加一，最后返回count。
