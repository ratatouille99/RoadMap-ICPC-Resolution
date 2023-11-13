# [Kadane's Algorithm](https://practice.geeksforgeeks.org/problems/kadanes-algorithm-1587115620/1)

```c++
class Solution{
    public:
    long long maxSubarraySum(int arr[], int n){
        long long maxSum = INT_MIN, actSum = 0;
        
        for(int i = 0; i < n; i++){
            actSum += arr[i];
            
            if(maxSum < actSum) maxSum = actSum;
            
            if(actSum < 0) actSum = 0;
        }
        
        return maxSum;
    }
};
```
