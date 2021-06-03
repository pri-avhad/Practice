# Title: String-Palindrome

Question link: https://leetcode.com/problems/longest-palindromic-substring/

### Code:

```
class Solution {
public:
    string longestPalindrome(string s) {
        int n = s.length();
        int max = 1, start = 0, end = 0;
        vector<vector<bool>> dp(n, vector<bool>(n, true));
        
        for(int length = 2; length <= n; length++) {
            for(int i = 0; i <= n - length; i++) {
                int j = i + length - 1;
                dp[i][j] = (length == 2) ? (s[i] == s[j]) : (s[i] == s[j] && dp[i+1][j-1]);
                if(dp[i][j] && max < length) start = i, end = j, max = length;
            }
        }
        s = s.substr(start, end - start + 1);
        return s;
    }
};
```

### Output:
![image](https://user-images.githubusercontent.com/64562764/120701234-38caf980-c4d0-11eb-95b0-f0e3b10c13ec.jpg)

### Comments:
Took way longer than expected!!!! **Revist question**
