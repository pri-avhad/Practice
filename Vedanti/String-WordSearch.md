# Title: String-WordSearch

Question link: https://leetcode.com/problems/word-search/

### Code:

```
bool helper(vector<vector<char>>& board,int i,int j, string &word,int id){
        if(id==word.size()-1) return true;
        board[i][j]-=65;
        
        if(i>0 && word[id+1]==board[i-1][j] && helper(board,i-1,j,word,id+1)) return true;
        if(j>0 && word[id+1]==board[i][j-1] && helper(board,i,j-1,word,id+1)) return true;
        if(i<board.size()-1 && word[id+1]==board[i+1][j] && helper(board,i+1,j,word,id+1)) return true;
        if(j<board[0].size()-1 && word[id+1]==board[i][j+1] && helper(board,i,j+1,word,id+1)) return true;
        
        board[i][j]+=65;
        return false;
    }
    bool exist(vector<vector<char>>& board, string word) {
        int r = board.size();
        int c= board[0].size();
        
        for(int i=0;i<r;i++){
            for(int j=0;j<c;j++){
                if(word[0]==board[i][j] && helper(board,i,j,word,0)) return true;
            }
        }
        return false; 
```

### Output:


### Comments:
was stuck because passed in 1 instead of zero in the exist function so the entire string wasnt getting checked in the helper function. 
