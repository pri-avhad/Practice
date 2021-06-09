# Title: String-Valid Parentheses

Question link: https://leetcode.com/problems/valid-parentheses/

### Code:

```
bool isValid(string s) {
        int n=s.size();
        if(n==1) return false;
        stack<char> st;
        for(int i=0;i<n;i++){
            char c=s[i];
            if(c=='(' || c=='[' || c=='{') st.push(c);
            else if(st.empty()) return false;
            else if((c==')' && st.top()=='(') || (c==']' && st.top()=='[') || (c=='}' && st.top()=='{')){
                st.pop();
            }
            else return false;
        }
        return st.empty();
```

### Output:


### Comments:
