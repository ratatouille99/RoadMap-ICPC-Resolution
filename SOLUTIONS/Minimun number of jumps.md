# [Minimum number of jumps][(https://practice.geeksforgeeks.org/problems/minimum-number-of-jumps-1587115620/1)
```c++
class Solution{
  public:
    int minJumps(int arr[], int n){
        int maximo = INT_MIN, dis = 0, jumps = 0;
        
        if(arr[0] == 0) return -1;
        
        for(int i = 0; i < n - 1 ; i++){
            
            maximo = max(maximo, i + arr[i]);
            
            if(i == dis){
                if (maximo == i && i != n - 1) return -1;
                
                jumps++;
                dis = maximo;
            }
 
        }
        
        return jumps;
    }
};
```
