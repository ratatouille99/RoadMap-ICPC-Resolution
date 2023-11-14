# [Merge Intervals](https://leetcode.com/problems/merge-intervals/)
```c++
class Solution {
public:
    vector<vector<int>> merge(vector<vector<int>>& intervals) {
        if(intervals.size() == 1) return intervals;

        vector<vector<int>>ans;
        int j = 0;

        sort(intervals.begin(), intervals.end());

        ans.push_back(intervals[0]);
        
        for(int i = 1; i < intervals.size(); i++){
            if(ans[j][1] >= intervals[i][0]){
                int x = ans[j][0], y = max(ans[j][1], intervals[i][1]);
                ans.pop_back();
                ans.push_back({x,y});
            }
            else{
                ans.push_back(intervals[i]);
                j++;
            }
        }

        return ans;
    }
};
```
