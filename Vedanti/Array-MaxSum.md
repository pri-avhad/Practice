# Title: Array-MaxSum

Question link: https://leetcode.com/problems/maximum-subarray/

### Code:

```
int maxSubArray(vector<int>& nums) {
        if(nums.size()==1) return nums[0];
        int n=nums.size();
        int ans;
        for(int i=1;i<n;i++){
            ans=max(nums[i-1]+nums[i],nums[i]);
            nums[i]=ans;
        }
        return (int)*max_element(nums.begin(),nums.end());
    }
//Copy paste your code here
```

### Output:


### Comments:
