# Title: Pascals Triangle

Question link: https://leetcode.com/problems/pascals-triangle/submissions/

### Code:

```
vector<vector<int>> ans;
        

        for(int i=1;i<=numRows;i++){
            int c=1;
            vector<int> v;
            for(int j=1;j<=i;j++){
                v.push_back(c);
                c=c*(i-j)/j;
            }
            ans.push_back(v);
        }
        return ans;
```

### Output:


### Comments:
