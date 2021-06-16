# Title: Array-Remove Duplicates

Question link: https://leetcode.com/problems/remove-duplicates-from-sorted-array/

### Code:

```
int removeDuplicates(vector<int>& nums) {
        nums.erase(unique(nums.begin(),nums.end()),nums.end());
        return nums.size();
        }
```

### Output:


### Comments:
i did cheating but ok. You solve this using two pointer, Vedanti!
