# Title: Array-Course Schedule

Question link: https://leetcode.com/problems/course-schedule-ii/

### Code:

```
class Solution {
public:
    vector<int> findOrder(int n, vector<vector<int>>& prerequisites) {
        vector<int> ans;
        vector<vector<int>> g(n);
        vector<int> degree(n,0);
        for(auto &i:prerequisites){
            int u=i[0];
            int v=i[1];
            g[u].push_back(v);
            degree[v]++;
        }
        queue<int> q;
        for(int i=0;i<n;i++){
            if(degree[i]==0){
                q.push(i);
            }
        }
        while(!q.empty()){
            int p=q.front();
            ans.push_back(p);
            q.pop();
            for(auto v:g[p]){
                degree[v]--;
                if(degree[v]==0){
                    q.push(v);
                }
            }
        }
        if(ans.size()!=n) return {};
        reverse(ans.begin(), ans.end());
        return ans;
	}
};
```

### Output:


### Comments:
