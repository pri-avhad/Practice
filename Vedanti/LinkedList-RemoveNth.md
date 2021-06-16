# Title: LinkedList-Remove Nth Node from the end

Question link: https://leetcode.com/problems/remove-nth-node-from-end-of-list/

### Code:

```
ListNode* p = head;
        ListNode* curr = head;
        for(int i=0;i<n;i++) {
            curr = curr->next;
        }
        if (curr == NULL) return head->next;
        while(curr->next!=NULL){
            curr= curr->next;
            p = p->next;
        }
        if(curr!=p) {
            p->next = p->next->next;
        }
        return head;
```

### Output:


### Comments:
