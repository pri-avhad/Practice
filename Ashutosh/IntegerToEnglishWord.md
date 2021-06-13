# Title: Integer to English Word

Question link: https://leetcode.com/problems/integer-to-english-words/

### Code:

class Solution {
public:
    string onesName(int n) {  // function for naming digits between 1 to 9
        switch(n) {
            case 1 : return "One";break;
            case 2: return "Two"; break;
            case 3: return "Three"; break;
            case 4: return "Four"; break;
            case 5: return "Five"; break;
            case 6: return "Six"; break;
            case 7: return "Seven"; break;
            case 8: return "Eight"; break;
            case 9: return "Nine"; break;
        }
        return "";
    }
    
    string tensName(int n) {  // function for naming digits 10, 20, 30... 90.
        switch(n) {
            case 1: return "Ten"; break;
            case 2: return "Twenty"; break;
            case 3: return "Thirty"; break;
            case 4: return "Forty"; break;
            case 5: return "Fifty"; break;
            case 6: return "Sixty"; break;
            case 7: return "Seventy"; break;
            case 8: return "Eighty"; break;
            case 9: return "Ninety"; break;
        }
        return "";
    }
    
    string giveThreeName(int n) {  // full name of digits from 1 to 100
        string res = "";
        if(n / 100 > 0)
            res += onesName(n / 100) + " Hundred";
        
        if(n / 100 > 0 && n % 100 > 0) res += " ";  // managing spaces
        
        int t = n % 100;
        if(t >= 20 || t <= 10) {
            if(t / 10 > 0)
                res += tensName(t / 10);
            
            if(t / 10 > 0 && t % 10 > 0) res += " ";
            
            if(t % 10 > 0)
                res += onesName(t % 10);
        }
        else {  // for the part where the tens number is between 11 to 19
            switch(t) {
                case 11: res += "Eleven"; break;
                case 12: res += "Twelve"; break;
                case 13: res += "Thirteen"; break;
                case 14: res += "Fourteen"; break;
                case 15: res += "Fifteen"; break;
                case 16: res += "Sixteen"; break;
                case 17: res += "Seventeen"; break;
                case 18: res += "Eighteen"; break;
                case 19: res += "Nineteen"; break;
            }
        }
        
        return res;
    }
    
    string numberToWords(int num) {
        if(num == 0) return "Zero";
        
        string res = "";
        res = giveThreeName(num % 1000) + res;
        num /= 1000;
        
        if(num > 0) {
            if(num % 1000 > 0)
                res = giveThreeName(num % 1000) + " Thousand " + res;
            num /= 1000;
        }
        
        if(num > 0) {
            if(num % 1000 > 0)
                res = giveThreeName(num % 1000) + " Million " + res;
            num /= 1000;
        }
        
        if(num > 0) {
            res = giveThreeName(num % 1000) + " Billion " + res;
        }
        
        if(res.back() == ' ') res.pop_back();
        
        return res;
    }
};
```

### Output:


### Comments:
