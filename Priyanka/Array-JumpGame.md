# Title: Array-JumpGame

Question link: https://leetcode.com/problems/jump-game/

### Code:

```
class Solution {
public:
    bool canJump(vector<int>& nums) {
        if(nums.size() == 1)
            return true;
        else if(nums[0] == 0)
            return false;
        int jumpPossibility = 0;
        for(int i = 0 ; i < nums.size() ; i++){
            if(i > jumpPossibility)
                return false;
            jumpPossibility = max(jumpPossibility , (nums[i] + i));
        }
       return true;
    }
};
```

### Output:
![image (4)](https://user-images.githubusercontent.com/64562764/120377921-63377e00-c33b-11eb-9de2-d9a361be61fc.png)

### Comments:
Easy to solve but wasn't able to come up with the easiest approach. <br/>Like directly considering the maximum possible! This made it so much easier to solve
