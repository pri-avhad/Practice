# Title: String-Letter Number

Question link: https://leetcode.com/problems/letter-combinations-of-a-phone-number/

### Code:

```
class Solution {
    void calling(string digits, unordered_map<char,string>mp , vector<string>&ans ,char u, int j, string gg)
    {
        if(j>=digits.size())
        {
            return;
        }
        string y=mp[u];
        for(int i=0;i<y.size();i++)
        {
            gg.push_back(y[i]);
            calling(digits,mp,ans,digits[j+1],j+1,gg);
            if(gg.size()==digits.size())
            {
                ans.push_back(gg);
            }
            gg.pop_back();
        }
    }
public:
    vector<string> letterCombinations(string digits) {
        unordered_map<char,string>mp;
        mp['2']="abc";
        mp['3']="def";
        mp['4']="ghi";
        mp['5']="jkl";
        mp['6']="mno";
        mp['7']="pqrs";
        mp['8']="tuv";
        mp['9']="wxyz";
        vector<string>ans;
        string gg;
        calling(digits,mp,ans,digits[0],0,gg);
        return ans;
    }
};
```

### Output:


### Comments:
