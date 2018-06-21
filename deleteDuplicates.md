# Practice
删除排序链表中的重复元素
## 问题
#### 
给定一个排序链表，删除所有重复的元素，使得每个元素只出现一次。
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
    ListNode* deleteDuplicates(ListNode* head) 
    {
         if (!head) return NULL;

         ListNode *p1 = head, *p2 = head->next;

    while (p1 && p2)
    {
        if (p1->val == p2->val)
        {
             p1->next = p2->next;
             p2 = p1->next;
        }
        else
        {
             p1 = p2;
             p2 = p1->next;
        }
     }
         return head;        
    }
};
## 总结体会：
维护两指针p1和p2，ListNode *p1, ListNode *p2，p2 始终指向 p1 的next，分别指向当前节点值和下一个节点，如果当前节点的值等于下一个节点的值，则p2的next赋给p1的next，p1的next赋给p2，如果不相等，则p2=p1,p1的next赋给p2。