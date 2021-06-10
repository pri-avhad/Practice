# Title: String-Valid Parentheses

Question link: https://leetcode.com/problems/valid-parentheses/

### Code:

```
class Solution {
public:
    bool isValid (string s) {
        unordered_map<char, char> brackets;
        brackets['{'] = '}';
        brackets['['] = ']';
        brackets['('] = ')';
        stack<char> st;
        for (int i = 0 ; i < s.size() ; i++) {
            if(brackets.find(s[i]) != brackets.end())
                st.push(s[i]);
            else if(!st.empty()) {
                char left = st.top();
                st.pop();
                char right = brackets[left];
                if(right != s[i])
                    return false;
            }
            else
                return false;
        }
        return st.empty();
    }
};
```

### Output:
![image (9)](https://user-images.githubusercontent.com/64562764/121533962-665afa00-ca1e-11eb-9b13-bb566bfa11d2.png)

### Comments:
Easy!!!
