# [Subarray with 0 sum](https://practice.geeksforgeeks.org/problems/subarray-with-0-sum-1587115621/1)
```c++
class Solution{
    public:
    //Complete this function
    //Function to check whether there is a subarray present with 0-sum or not.
    bool subArrayExists(int arr[], int n)
    {
        unordered_set<int>s{0};
        int sum = 0;
        
        for(int i = 0; i < n ; i++){
            sum += arr[i];
            
            if(s.find(sum) == s.end()) s.insert(sum);
            else return true;
        }
        
        return false;
    }
};
```
