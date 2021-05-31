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
![Capture](https://user-images.githubusercontent.com/64562764/120232319-f3f55780-c270-11eb-81f5-7bc40aafa6d1.PNG)


### Comments:
Nothing or remember size .,fs;lfjowif
