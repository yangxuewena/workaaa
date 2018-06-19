# Practice
合并两个有序链表
## 问题
#### 
将两个有序链表合并为一个新的有序链表并返回。新链表是通过拼接给定的两个链表的所有节点组成的。
## 编程实现：
/**   
 
  * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:

    ListNode* mergeTwoLists(ListNode* l1, ListNode* l2) 
    {
        ListNode *l = new ListNode(0);  
        if (l1 == NULL) return l2;  
        if (l2 == NULL) return l1;  
        if (l1->val < l2->val)  
        {  
            l->val = l1->val;  
            l->next = mergeTwoLists(l1->next, l2);  
        }  
        else  
        {  
            l->val = l2->val;  
            l->next = mergeTwoLists(l1, l2->next);  
        }  
        return l;  
        
    }

};
## 总结体会：
若链表l1为空，返回链表l2;若链表l2为空，返回链表l1;每次判断两个链表的头部小的数值，存取小的，并让该链表往后移动。