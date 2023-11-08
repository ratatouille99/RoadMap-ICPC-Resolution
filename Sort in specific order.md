## [Sort in specific order](https://practice.geeksforgeeks.org/problems/sort-in-specific-order2422/1)
```c++
#include <bits/stdc++.h>
using namespace std;

class Solution
{
  public:
    void sortIt(long long arr[], long long n)
    {
        vector<long long>odds, even;
        int idx = 0;
         
        for(int i = 0; i < n; i++){
            if(arr[i] % 2) odds.push_back(arr[i]);
            else even.push_back(arr[i]);
        }
         
        sort(odds.rbegin(), odds.rend());
        sort(even.begin(), even.end());
         
        for(auto &a : odds){
            arr[idx] = a;
            idx++;
        }
        
        for(auto &a : even){
            arr[idx] = a;
            idx++;
        }
    }
};

int main() {
    long long t;
    cin >> t;
    while (t--) {
        long long n;
        cin >> n;
        long long arr[n];

        for (int i = 0; i < n; i++) 
            cin >> arr[i];
        
        Solution ob;
        ob.sortIt(arr, n);

        for (int i = 0; i < n; i++)
            cout << arr[i] << " ";
        cout << endl;
    }
    return 0;
}
```
