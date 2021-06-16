# Title: Array-Search Insert 

Question link: https://leetcode.com/problems/search-insert-position/

### Code:

```
int searchInsert(vector<int>& nums, int target) {
        for(int i=0;i<nums.size();i++){
            if(nums[i]==target) return i;
        }
        return(lower_bound(nums.begin(),nums.end(),target)-nums.begin());
    }
```

### Output:


### Comments:
