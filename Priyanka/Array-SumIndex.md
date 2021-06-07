# Title:  Array-SumIndex

Question link: https://leetcode.com/problems/two-sum/

### Code
```
#define dict unordered_map<ll, int>
#define ll long long int
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        ll n=nums.size();
        dict map={};
        for(ll i=0; i<n; i++){
            if(map.count(nums[i]))
                return {map[nums[i]], (int)i};
            map[target-nums[i]]=i;
        }
        return {};
    }
};
```

### Output:
![image (8)](https://user-images.githubusercontent.com/64562764/121075841-4d223580-c7f3-11eb-8f83-64dd715e9fd7.png)

### Comments:
Used dictionary!
