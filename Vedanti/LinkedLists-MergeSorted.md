# Title: LinkedLists-MergeSorted

Question link: https://leetcode.com/problems/merge-two-sorted-lists/

### Code:

```
ListNode* mergeTwoLists(ListNode* l1, ListNode* l2) {
        if(!l1 && !l2) return l1;
        if(!l1) return l2;
        if(!l2) return l1;
        ListNode* p=l1;
        vector<int> v;
        while(p->next){
            v.push_back(p->val);
            p=p->next;
        }
        p->next=l2;
        while(p){
            v.push_back(p->val);
            p=p->next;
        }
        sort(v.begin(),v.end());
        ListNode* ans=l1;
        int i=0;
        while(ans){
            ans->val=v[i];
            ans=ans->next;
            i++;
        }
        return l1;
    }
```

### Output:


### Comments:
