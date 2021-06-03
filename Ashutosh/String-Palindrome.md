# Title: String-Palindrome

Question link: https://leetcode.com/problems/longest-palindromic-substring/

### Code:

```
class Solution {
public:
    string longestPalindrome(string s) {
         int n=s.size();
        bool dp[n][n];
        memset(dp, false, sizeof(dp));
        int cnt=1;
        for(int i=0;i<n;i++){
            dp[i][i]=true;
        }
        int start=0;
        for(int i=0;i<n-1;i++){
            if(s[i]==s[i+1]){
                dp[i][i+1]=true;
                start=i;
                cnt=2;
            }
        }
        
        for(int i=3;i<=n;i++){
            for(int j=0;j<n-i+1;j++){
                int k=i+j-1;
                
                if(s[j]==s[k] && dp[j+1][k-1]){
                    dp[j][k]=true;
                    if(cnt<i){
                        cnt=i;
                        start=j;
                    }
                }
            }
        }
        string res="";
        for(int i=start;i<start+cnt;i++){
            res+=s[i];
        }
        return res;
    }
};

```

### Output:
![Screenshot (494)](https://user-images.githubusercontent.com/68456662/120599992-d9d09a80-c465-11eb-9822-e67896784c37.png)


### Comments:
