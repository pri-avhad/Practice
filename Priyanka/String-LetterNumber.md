# Title: String-Letter Number

Question link: https://leetcode.com/problems/letter-combinations-of-a-phone-number/

### Code:

```
class Solution {
    vector<string> v;
    public:
    int combinations(char* digit, map<int, vector<string>> &map, int s){
        if(s==0)
            return 0;        
        int size = combinations(digit + 1, map, s - 1);
        vector<string> op;
        int dig = digit[0] - '0';
        op = map[dig];
        if(size == 0)
        {
            v = op;
            return op.size();
        }
        vector<string> v2 = v;
        v.clear();
        for(int i = 0; i < op.size(); i++){
            string a = op[i];
            for(int j = 0; j <v2.size(); j++){
                string s = a + v2[j];
                v.push_back(s);
            }
        }       
        return v.size();
    }
    
    vector<string> letterCombinations(string digits) {
        map<int, vector<string>> map;
        map[2] = {"a","b","c"};
        map[3] = {"d","e","f"};
        map[4] = {"g","h","i"};
        map[5] = {"j","k","l"};
        map[6] = {"m","n","o"};
        map[7] = {"p","q","r" ,"s"};
        map[8] = {"t","u","v"};
        map[9] = {"w","x","y","z"};
        if(digits.length() == 0)
            return {};
        else if(digits.length() == 1){
            int a  = digits[0] - '0';
            return map[a];
        }
        int a = digits.length();
        char dig[5];
        for(int i = 0; i < a; i ++)
            dig[i] = digits[i];
        a = combinations(dig,map, digits.length());
        return v;
    }
};
```

### Output:
![image (10)](https://user-images.githubusercontent.com/64562764/121535358-b71f2280-ca1f-11eb-8c27-ceaefe2b4c4d.png)

### Comments:
![image](https://user-images.githubusercontent.com/64562764/121535116-7a532b80-ca1f-11eb-9825-a29c141ff9da.png)
Will redo
