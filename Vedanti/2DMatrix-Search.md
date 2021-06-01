# Title: Matrix-Search 2D array

Question link: https://leetcode.com/problems/search-a-2d-matrix-ii/

### Code:

```
bool searchMatrix(vector<vector<int>>& matrix, int target) {
        int i=0,j=matrix[0].size()-1;
        while(i<matrix.size() && j>=0){
            if(matrix[i][j]==target) return true;
            else if(matrix[i][j]>target) j--;
            else i++;
        }
       return false; 
    }
```

### Output:


### Comments:
