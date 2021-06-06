# Title: Array-MaxSum

Question link: https://leetcode.com/problems/maximum-subarray/

### Code:

```
class Solution {
public:
    int maxSubArray(vector<int>& nums) {
        int sum = nums[0], result = nums[0];        
        for (int i = 1; i < nums.size(); i++) {
            sum = max(nums[i], sum + nums[i]);
            result = max(result, sum);
        }
        return result;
    }
};
```

### Output:
![image (7)](https://user-images.githubusercontent.com/64562764/120939501-fe629600-c735-11eb-9177-e60a70365e13.png)

### Comments:
Easy! Need to revise DP
