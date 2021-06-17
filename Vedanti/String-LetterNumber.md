# Title: String-Letter Number

Question link: https://leetcode.com/problems/letter-combinations-of-a-phone-number/

### Code:

```
string alpha[10]={"0","1","abc","def","ghi","jkl","mno","pqrs","tuv","wxyz"}; 
    void backtrack(string digits,string curr, vector<string> &res){
        if(digits.size()==0) {
            res.push_back(curr);
            return;
        }
        int l=digits[0]-'0';
        
        for(int i=0;i<alpha[l].size();i++)
        {
            backtrack(digits.substr(1),curr+alpha[l][i],res);
        }
        
    }
    vector<string> letterCombinations(string digits) {
        vector<string> res;
        if(digits!="") backtrack(digits,"",res);
        return res;
    }
```

### Output:


### Comments:
