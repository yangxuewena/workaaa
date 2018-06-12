# Practice
实现 strStr() 函数。
## 问题
#### 
给定一个 haystack 字符串和一个 needle 字符串，在 haystack 字符串中找出 needle 字符串出现的第一个位置 (从0开始)。如果不存在，则返回  -1。
## 编程实现：
class Solution {
public:

    int strStr(string haystack, string needle) 
    {
         int i, j, m = haystack.length(), n = needle.length();
         if (n == 0)  return 0;
         for (i = 0; i <=m - n; i++)
		 {
            for (j = 0; j < n; j++) 
                if (haystack[i + j] !=  needle[j]) 
					break;
                if (j == n)  
					return i;
         }
         return -1;
        
    }
};
## 总结体会：
当 needle 是空字符串时返回 0 。两重循环，找出needle字符串在haystack字符串中的第一个位置。