# Title: Matrix-Search 2D array

Question link: https://leetcode.com/problems/search-a-2d-matrix-ii/

### Code:

```
class Solution {
public:
    int reverse(int x) {
        int rev = 0;
        while(x!=0){
            if (rev > INT_MAX/10 || (rev == INT_MAX / 10 && (x % 10) > 7)) 
                return 0;
            if (rev < INT_MIN/10 || (rev == INT_MIN / 10 && (x % 10) < -8)) 
                return 0;
            rev = rev * 10 + x % 10;
            x/=10;
        }
        return rev;
    }
};
```

### Output:
![image](https://user-images.githubusercontent.com/64562764/120231307-babbe800-c26e-11eb-83a4-2fe79720d0d6.png)


### Comments:
Nothing
Or remember to see complexity
