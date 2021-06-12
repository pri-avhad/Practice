# Title: Array-Course Schedule

Question link: https://leetcode.com/problems/course-schedule-ii/

### Code:

```
class Solution {
public:
    vector<int> findOrder(int n, vector<vector<int>>& prerequisites) {
        vector<vector<int>> g(n);
        vector<int> order, degree(n , 0);
        for(auto &i : prerequisites){
            int u = i[0];
            int v = i[1];
            g[u].push_back(v);
            degree[v]++;
        }
        queue<int> q; 
        for(int i = 0 ; i < n ; i++){
            if(degree[i] == 0)
                q.push(i);
        }
        while(!q.empty()){
            int p = q.front();
            order.push_back(p);
            q.pop();
            for(auto v : g[p]){
                degree[v]--;
                if(degree[v] == 0)
                    q.push(v);
            }
        }
        if(order.size() != n) 
            return {};
        reverse(order.begin(), order.end());
        return order;
	}
};
```

### Output:
![image (11)](https://user-images.githubusercontent.com/64562764/121774931-5835e680-cba2-11eb-8739-a7e9960509b1.png)

### Comments:
Took way longer than it should have! The while loop part where we form the order I was trying to do it without using queue and was stuck.
