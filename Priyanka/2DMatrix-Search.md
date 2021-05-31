# Title: Matrix-Search 2D array

Question link: https://leetcode.com/problems/search-a-2d-matrix-ii/

### Code:

```
class Solution {
public:
    bool searchMatrix(vector<vector<int>>& matrix, int target) {
        int m = matrix.size(), n = matrix[0].size();
        for(int i = 0, j = (n - 1); (i < m && j >= 0);){
            if(matrix[i][j] == target) 
                return true;
            else if(matrix[i][j] > target) 
                j--;
            else 
                i++;
        }
        return false; 
    }
};
```

### Output:
![image](https://user-images.githubusercontent.com/64562764/120238814-9d8d1680-c27a-11eb-9c7d-479d9408a9fb.png)

### Comments:
Traversal need not be 0 to something or the other way around always! And it shouldn't always start at the [0,0]

Here the traversal was interesting 

![image (3)](https://user-images.githubusercontent.com/64562764/120239121-40459500-c27b-11eb-95aa-a336619e79fc.png)


And the time complexity is just O(m+n)
