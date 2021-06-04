# Title: LinkedLists-MergeSorted

Question link: https://leetcode.com/problems/merge-two-sorted-lists/

### Code:

```
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode() : val(0), next(nullptr) {}
 *     ListNode(int x) : val(x), next(nullptr) {}
 *     ListNode(int x, ListNode *next) : val(x), next(next) {}
 * };
 */
class Solution {
public:
    ListNode* mergeTwoLists(ListNode* l1, ListNode* l2) {
        if(l1 == NULL)
            return l2;
        else if(l2 == NULL)
            return l1;        
        ListNode *l;
        if(l1->val <= l2->val)
        {
            l = l1;
            l1 = l1->next;
        }
        else
        {
            l = l2;
            l2 = l2->next;
        }
        ListNode *ptr = l;
        while(l1 != NULL && l2 != NULL)
        {
            if(l1->val <= l2->val)
            {
                ptr->next = l1;
                ptr = l1;
                l1 = l1->next;
            }
            else
            {
                ptr->next = l2;
                ptr = l2;
                l2 = l2->next;
            }
        }
        while(l2 != NULL)
        {
            ptr->next = l2;
            ptr = l2;
            l2 = l2->next;   
        }
        while(l1 != NULL)
        {
            ptr->next = l1;
            ptr = l1;
            l1 = l1->next;
        }
        ptr->next = NULL;
        return l;
    }
};
```

### Output:
![image (5)](https://user-images.githubusercontent.com/64562764/120835486-01b52080-c582-11eb-965f-de218d24430b.png)

### Comments:
Great revision!! Took only 10 mins. 
