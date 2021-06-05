# Title: LinkedLists-MergeSorted

Question link: https://leetcode.com/problems/merge-two-sorted-lists/

### Code:

```
class Solution {
public:
    ListNode* mergeTwoLists(ListNode* l1, ListNode* l2) {
        if (l1==NULL){
            return l2;
        }
        if (l2==NULL){
            return l1;
        }
        
        if(l1->val > l2->val){
            std::swap(l1,l2);
        }
        ListNode * res=l1;
        while(l1 != NULL && l2 != NULL){
            ListNode * tmp=NULL;
            while(l1 != NULL && l1 -> val <= l2 -> val){
                tmp=l1;
                l1=l1->next;
            }
            tmp->next=l2;
            std::swap(l1,l2);
        }
        return res;
    }
};

```

### Output:
![Screenshot (499)](https://user-images.githubusercontent.com/68456662/120891833-54491800-c628-11eb-9a2e-ee5905fb22a0.png)


### Comments:
