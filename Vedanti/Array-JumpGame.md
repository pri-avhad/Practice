# Title: Array-JumpGame

Question link: https://leetcode.com/problems/jump-game/

### Code:

```
bool canJump(vector<int>& nums) {
        int i=0,n=nums.size(),m=0;
        if(n==1) return true;
        while(i<n && i<=m){
            m=max(nums[i]+i, m);
            i++;
        }
        return (i==n);
    }
```

### Output:


### Comments:
