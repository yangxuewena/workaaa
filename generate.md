# Practice
杨辉三角
## 问题
#### 
给一个非负整数 num，反复添加所有的数字，直到结果只有一个数字。给定一个非负整数 numRows，生成杨辉三角的前 numRows 行
## 编程实现：
class Solution {
public:

    vector<vector<int>> generate(int numRows) 
    {
        vector<vector<int>> a(numRows);  
        for(int i=0;i<numRows;i++) {  
            a[i].resize(i+1);  
            a[i][0]=a[i][i]=1;  
            if(i>1)
            {  
                int j;  
                for(j=1;j<=i/2;j++){  
                    a[i][j]=a[i-1][j-1]+a[i-1][j];  
                    a[i][i-j]=a[i][j];  
                }  
            }  
        }  
        return a;  
        
    }
};
## 总结体会：
初始化三角形腰上的1，然后利用上一层的数字逐层计算。 