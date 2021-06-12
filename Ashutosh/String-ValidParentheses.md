# Title: String-Valid Parentheses

Question link: https://leetcode.com/problems/valid-parentheses/

### Code:

 class Solution {
public:
bool isValid(string s) {

    stack<char> st;
    
    map<char, char> m;
    
    m[')'] = '(';
    m['}'] = '{';
    m[']'] = '[';
    
    if(s.size() == 1){
        
        return false;
    }
    
    for(auto x: s)
    {
        if(x == '(' || x == '{' || x == '['){
            
            st.push(x);
        }
        else{
            
            if(!st.empty( ) && m[x] == st.top( )){
                
                st.pop( );
            }
            else{
                
                return false;
            }
        }
    }
    
    return st.empty( );
}
};
```

### Output:


### Comments:
