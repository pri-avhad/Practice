# Title: Integer to English Word

Question link: https://leetcode.com/problems/integer-to-english-words/

### Code:

```
class Solution {
public:
    string digits[20] = {"", "One", "Two", "Three", "Four", "Five", "Six", "Seven", "Eight", "Nine", "Ten", "Eleven", "Twelve", "Thirteen", "Fourteen", "Fifteen", "Sixteen", "Seventeen", "Eighteen", "Nineteen"};
    string tens[10] = {"", "Ten", "Twenty", "Thirty", "Forty", "Fifty", "Sixty", "Seventy", "Eighty", "Ninety"};
    string numberToWords(int num) {
        if(num == 0) return "Zero";
        else return int2string(num).substr(1);
    }
    string int2string(int n){
        if(n >= 1000000000) return int2string(n / 1000000000) + " Billion" + int2string(n % 1000000000);
        else if(n >= 1000000) return int2string(n / 1000000) + " Million" + int2string(n % 1000000);
        else if(n >= 1000) return int2string(n / 1000) + " Thousand" + int2string(n % 1000);
        else if(n >= 100) return int2string(n / 100) + " Hundred" + int2string(n % 100);
        else if(n >= 20) return " " + tens[n / 10] + int2string(n % 10);
        else if(n >= 1) return " " + digits[n];
        else return "";
    }    
};
```

### Output:
![image (14)](https://user-images.githubusercontent.com/64562764/121859950-fa2a1000-cd15-11eb-98f1-c3eb9ac82f78.png)

### Comments:
I thought it was complicated pehle and now it is faster than 100%. So much for not trying at all XD
