# Title: Array-Remove Duplicates

Question link: https://leetcode.com/problems/remove-duplicates-from-sorted-array/

### Code:

```
class Solution {
public:
    int removeDuplicates(vector<int>& nums) {
        set s(nums.begin(), nums.end());
        nums.clear();
        for(auto x :s)
            nums.push_back(x);
        return s.size();
    }
};
```

### Output:
![image (12)](https://user-images.githubusercontent.com/64562764/121818984-48a0c580-cca8-11eb-9fec-c02145f2471c.png)

### Comments:
![image](https://user-images.githubusercontent.com/64562764/121818892-b7315380-cca7-11eb-9f7a-65ec1c935c32.png)
<br/>Honestly I like this one though. But ay sets made more sense.
