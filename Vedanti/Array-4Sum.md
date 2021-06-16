# Title: Array-4 Sum

Question link: https://leetcode.com/problems/4sum/

### Code:

```
vector<vector<int>> fourSum(vector<int>& nums, int target) {
        vector<vector<int>> ans;
        if(nums.size()<4) return ans;
        map<vector<int>,int> m;
        set<vector<int>>s;
        sort(nums.begin(),nums.end());
        for(int i=0;i<nums.size()-1;i++){
            for(int j=i+1;j<nums.size();j++){
                int sum=nums[i]+nums[j];
                m[{i, j}]= sum;
            }
        }
        
        for(auto it:m){
            int t=it.second;
            //cout<<it.second<<" ";
            int i=0,j=nums.size()-1;
            
                while(i<j){
                    int sum = t+nums[i]+nums[j];
                    //cout<<i<<" "<<j<<" "<<it.first[0]<<" "<<it.first[1]<<"\n";
                    if(sum==target && i!=it.first[0] && j!=it.first[1] && i!=it.first[1] && j!=it.first[0]){
                        ans.push_back({nums[i],nums[j],nums[it.first[0]],nums[it.first[1]]});
                        j--;
                      
                    }
                    else if(sum>target) j--;
                    else i++;
                }
            }
            
        
        for(int i=0;i<ans.size();i++) {
            sort(ans[i].begin(),ans[i].end());
            s.insert(ans[i]);
        }
        vector<vector<int>> res;
        for(auto it:s) res.push_back(it);
        return res;
    }
```

### Output:


### Comments:
