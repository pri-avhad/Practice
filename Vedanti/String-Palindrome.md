# Title: String-Palindrome

Question link: https://leetcode.com/problems/longest-palindromic-substring/

### Code:

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
        string ans="";
        for(int i=start;i<start+cnt;i++){
            ans+=s[i];
        }
        return ans;
    }
    
### Output:


### Comments:
