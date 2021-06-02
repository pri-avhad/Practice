# Title: Array-JumpGame

Question link: https://leetcode.com/problems/jump-game/

### Code:

```
class Solution {
public:
    bool canJump(vector<int>& nums) {
    int n = nums.size();
    int reach = 0;
    
    for(int i=0 ; i<n ; ++i){
        if (reach < i)
            return false;
        reach = max(reach,i+nums[i]);
    }
    return true;
    }
};
```

### Output:
![Screenshot (491)](https://user-images.githubusercontent.com/68456662/120506280-66864480-c3e3-11eb-950d-9a114ee7f458.png)


### Comments:
time complexity is O(n)
space complexity is O(1)
