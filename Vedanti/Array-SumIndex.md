# Title:  Array-SumIndex

Question link: https://leetcode.com/problems/two-sum/

### Code
```
 vector<int> twoSum(vector<int>& nums, int target) {
        vector<int> ans;
        map<int,int> m;
        for(int i=0;i<nums.size();i++){
            int n=target-nums[i];
            if(m.find(n)!=m.end()){
                ans.push_back(i);
                ans.push_back(m[n]);
                break;
            }
            else m[nums[i]]=i;
        }
        return ans;
   }
```

### Output:


### Comments:
