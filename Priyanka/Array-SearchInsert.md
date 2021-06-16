# Title: Array-Search Insert 

Question link: https://leetcode.com/problems/search-insert-position/

### Code:

```
class Solution {
public:
    int searchInsert(vector<int>& nums, int target) {
        int start = 0, end = nums.size() - 1, mid = floor((start + end)/2);
        if(target > nums[end])
            return end + 1;
        else if(target < nums[start])
            return start;
        while(start <= end){
            mid = floor((start + end)/2);
            if(target < nums[mid])
                end = mid - 1;
            else if(target > nums[mid])
                start = mid + 1;
            else if(target == nums[mid])
                return mid;            
        }
        return start; 
    }
};
```

### Output:
![image (15)](https://user-images.githubusercontent.com/64562764/122201390-9c362d80-ceb9-11eb-82c9-02fb18c33671.png)

### Comments:
Wtf is wrong with me!!!! Why did I do so many faltu mistakes. Was easy and took 6 mins
