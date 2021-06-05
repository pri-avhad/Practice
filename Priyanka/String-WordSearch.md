# Title: String-WordSearch

Question link: https://leetcode.com/problems/word-search/

### Code:

```
class Solution {
public:
    void backtrack(vector<vector<char>> &board, string &word, bool &found, int i, int j){
        if (found)
            return;
        char letter = word.back(); 
        if (board[i][j] != letter)
            return;
        word.pop_back();
        if (word.compare("") == 0)
        {
            found = true;
            return;
        }
        board[i][j]= '.';
        if (i + 1 < board.size() && board[i+1][j] != '.')
            backtrack(board, word, found, i + 1, j);   
        if (i - 1 >= 0 && board[i-1][j] != '.')
            backtrack(board, word, found, i - 1, j);
        if (j + 1 < board.at(0).size() && board[i][j+1] != '.')
            backtrack(board, word, found, i, j + 1);
        if (j - 1 >= 0 && board[i][j-1] != '.')
            backtrack(board, word, found, i, j - 1);
        board[i][j] = letter;
        word.push_back(letter);
    }    
    bool exist(vector<vector<char>>& board, string word) {
        bool found = false;
        for (int i = 0; i < board.size(); i++)
        {
            for (int j = 0; j < board[0].size(); j++)
                backtrack(board, word, found, i, j);
        }
        return found;
    }
};
```

### Output:
![image (6)](https://user-images.githubusercontent.com/64562764/120903141-04874280-c662-11eb-82e4-a0ed0544c1a0.png)

### Comments:
Definetely did not consider backtracking at first and just went on with the grunt to check every adjacent letter.
Will have to do more of backtracking
