# Practice
二叉树的最大深度
## 问题
#### 
给定一个二叉树，找出其最大深度。

二叉树的深度为根节点到最远叶子节点的最长路径上的节点数。
## 编程实现：
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode(int x) : val(x), left(NULL), right(NULL) {}
 * };
 */
class Solution {
public:

    int maxDepth(TreeNode* root)
    {
        if(root)
        {
            int left = maxDepth(root->left)+1;
            int right = maxDepth(root->right)+1;
            return left>right ? left : right;
        }
        else
            return 0;
        
    }
};
## 总结体会：
求最大深度，是要从根节点开始，用递归，只要知道左子树和右子树的最大深度，再加上1，就是这个二叉树的最大深度，直到递归到最后一层。