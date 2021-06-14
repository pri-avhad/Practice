# Title: LinkedList-Remove Nth Node from the end

Question link: https://leetcode.com/problems/remove-nth-node-from-end-of-list/

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
    ListNode* removeNthFromEnd(ListNode* head, int n) {
        ListNode* temp = head;
        int l = 1;
        while(temp->next != nullptr){
            temp = temp->next;
            l++;
        }
        temp = head;
        for(int i = 1 ; i < (l-n) ; i++)
            head = head->next;   
        if(l == 1){
            head = nullptr;
            temp = head;
        }     
        else if((l-n) == 0){
            head = head->next;
            temp = head;
        }
        else
            head->next = head->next->next;
        return temp;
    }
};
```

### Output:
![image (13)](https://user-images.githubusercontent.com/64562764/121856477-293e8280-cd12-11eb-9dac-ad375bb66d86.png)

### Comments:
Was damn easy but still fucked up 2 cases cause of not reading the whole thing
