# [Common elements](https://practice.geeksforgeeks.org/problems/common-elements1132/1)
```c++
class Solution
{
    public:    
       vector <int> commonElements (int A[], int B[], int C[], int n1, int n2, int n3)
        {
            vector<int>ans;
            int i = 0, j = 0, k = 0, aux = 0;
            
            while(i < n1 && j < n2 && k < n3){
                if(A[i] == B[j] && A[i] == C[k]){
                    aux = A[i];
                    
                    if(ans.empty()) ans.push_back(A[i]);
                    else if(ans.back() != aux) ans.push_back(A[i]);
                    
                    i++;
                    j++;
                    k++;
                }
                
                int actMax = max(A[i], max(B[j], C[k]));
            
                while(i < n1 && actMax > A[i]) i++;
                while(j < n2 && actMax > B[j]) j++;
                while(k < n3 && actMax > C[k]) k++;
            }
            
            return ans;
        }

};
```
