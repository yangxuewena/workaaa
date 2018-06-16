# Practice
翻转二叉树
## 问题
#### 
翻转一棵二叉树
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

    TreeNode* invertTree(TreeNode* root) 
    {
        TreeNode *temp;
        if(NULL!=root){
            temp=root->left;
            root->left=root->right;
            root->right=temp;
            invertTree(root->left);
            invertTree(root->right);
        }
        return root;

    }
};
## 总结体会：
对于任意一个结点，先将其左子树调用当前函数完成翻转，再将其右子树调用当前函数完成翻转。然后交换左右子树，返回这个结点即可。递归的终点是判断给的结点值是否为空，如果为空说明到达叶结点的子树了，直接返回空就行了。