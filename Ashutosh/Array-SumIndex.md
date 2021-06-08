# Title:  Array-SumIndex

Question link: https://leetcode.com/problems/two-sum/

### Code
```
class Solution {
    public int[] twoSum(int[] nums, int target) {
        int[] res = new int[2];
        Map<Integer,Integer> map = new HashMap<Integer,Integer>();
        
            
        
        for(int i=0;i<nums.length;i++){
            int find = target - nums[i];
            
            if(map.containsKey(find)){
                res[0] = map.get(find);
                res[1] = i;
                return res;
            }
            else{
                map.put(nums[i],i);
            }
            
        }
        return res;
    }
}
```

### Output:


### Comments:
