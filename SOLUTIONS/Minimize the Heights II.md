# [Minimize the Heights II](https://practice.geeksforgeeks.org/problems/minimize-the-heights3351/1)

```c++
class Solution {
  public:
    int getMinDiff(int a[], int n, int k) {
        int i;
        sort(a, a+n);
        
        int ans = a[n-1] - a[0];
        int maxh, minh;
        
        for(int i = 1; i < n ; i++){
            maxh = max(a[n-1]-k, a[i-1]+k);
            minh = min(a[0] + k, a[i] - k);
            
            if(minh < 0) continue;
            
            ans = min(ans, maxh - minh);
        }
        
        return ans;
    }
};
```
