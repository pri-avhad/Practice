# Title: Array-JumpGame

Question link: https://leetcode.com/problems/basic-calculator-ii/

### Code:

```
class Solution {
public:
    int getPriority(char &c) {
        if(c == '+' || c == '-')
            return 0;
        else
            return 1;
    }
    
    int perform_op(char &c, int &a, int &b) {
        if(c == '+')
            return a + b;
        else if(c == '-')
            return a - b;
        else if(c == '*')
            return a * b;
        else
            return a / b;
    }
    
    int calculate(string s) {
        stack<int> nums;
        stack<char> ops;
        
        for(int i = 0; i < s.size(); ) {
            while(i < s.size() && s[i] == ' ') i++;
            if(i < s.size() && isdigit(s[i])) {
                int number = 0;
                while(i < s.size() && isdigit(s[i])) {
                    number = number * 10 + (s[i] - '0');
                    i++;
                }
                nums.push(number);
            }
        
            else if(i < s.size() ) {
                while(!ops.empty() && getPriority(s[i]) <= getPriority(ops.top())) {
                    int second = nums.top(); nums.pop();
                    int first = nums.top(); nums.pop();
                    nums.push(perform_op(ops.top(), first, second));
                    ops.pop();
                }
                ops.push(s[i]);
                i++;
            }
        }
        
        
        while(!ops.empty()) {
            int second = nums.top(); nums.pop();
            int first = nums.top(); nums.pop();
            nums.push(perform_op(ops.top(), first, second));
            ops.pop();
        }
        
        return nums.top();
    }
};
    
```

### Output:


### Comments:
