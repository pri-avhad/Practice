# Title: String-WordSearch

Question link: https://leetcode.com/problems/word-search/

### Code

class Solution {
public:
    
    vector<vector<bool>> visited;
    
    bool valid(int i, int j) {
        if(i<0 || i>=visited.size() || j<0 || j>visited[0].size()) return false;
        return !visited[i][j];
    }
    
    bool jump(vector<vector<char>>& board, int i, int j, const char *word, int len)
    {
        int Di[] = {0,1,0,-1}; 
        int Dj[] = {1,0,-1,0};
        
        if(!valid(i,j)) return false;
        if(len == 1) return (word[0] == board[i][j]);
        else if(word[len-1] != board[i][j]) return false;

        visited[i][j] = true;
        
        for(int dir=0; dir<4; ++dir) {
            if(jump(board, i+Di[dir], j+Dj[dir], word, len-1)) {
                visited[i][j] = false;
                return true;
            }                     
        }
        
        visited[i][j] = false;
        return false;
    }
    
    bool exist(vector<vector<char>>& board, string word) 
    {
        if(word.empty()) return false;
        
        visited.resize(board.size(),vector<bool>(board[0].size(),false));
        
        for(int i=0; i<board.size(); ++i) {
            for(int j=0; j<board[0].size(); ++j) {
                if(jump(board,i,j,word.c_str(),word.size())) return true;
            }
        }

        return false;
    }
};

```

### Output:
![Screenshot (501)](https://user-images.githubusercontent.com/68456662/120891963-3af49b80-c629-11eb-8b58-900fe3ec634a.png)


### Comments:
