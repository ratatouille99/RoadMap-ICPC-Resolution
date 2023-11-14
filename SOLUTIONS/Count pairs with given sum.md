# [Count pairs with given sum](https://practice.geeksforgeeks.org/problems/count-pairs-with-given-sum5022/1)
```c++
class Solution{   
public:
    int getPairsCount(int arr[], int n, int k) {
        unordered_map<int,int>dif;
        int ans = 0;
        
        for(int i = 0; i < n; i++)dif[arr[i]]++;
        
        for(int i = 0; i < n; i++){
            int aux = k - arr[i];
            
            if(dif.count(aux) > 0){
                dif[arr[i]]--;
                ans += dif[aux];
            }
        }
        
        return ans;
    }
};
```
