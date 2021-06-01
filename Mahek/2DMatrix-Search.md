# Title: Matrix-Search 2D array

Question link: https://leetcode.com/problems/search-a-2d-matrix-ii/

### Code:

```
class Solution {
public:
    
    bool searchMatrix(vector<vector<int>>& matrix, int target) {
        int c= 0;
        int r= matrix.size()-1;
        
        while(r >= 0 and c < matrix[0].size()){
            if (matrix[r][c] == target)
                return true;
            else if (matrix[r][c] > target)
                r--;
            else
                c++;
        }
        return false;
    }
};
```

### Output:
![image](https://user-images.githubusercontent.com/64473654/120380359-b19a4c00-c33e-11eb-850b-40e7da75a633.png)

### Comments:
Logic :

[[1,   4,  7, 11, 15],
  
  [2,   5,  8, 12, 19],
  
  [3,   6,  9, 16, 22],
  
  [10, 13, 14, 17, 24],
  
  [18, 21, 23, 26, 30]]

- Target = 19.
- Start with 18.
- 18 is smaller than 19. All the elements in the first column are smaller than 18, so 19 cannot be in the first column, hence move right, which is 21.
- 21 is bigger than 19. All the elements in the same row to the right of 21 are bigger than 21 so 19 cannot be in this row, hence move up, which is 13.
- Likewise, 14->17->24->22->19.
