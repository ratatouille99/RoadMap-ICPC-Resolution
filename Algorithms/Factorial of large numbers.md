# Factorials of large numbers
The reason why we implement a special algorithm to be able to find the factorial of large numbers is that if this is done in a normal recursive way the computational cost would be enormous, in addition to the fact that the "int" type is not sufficient to be able to store such values.

```c++
class Solution {
public:
    vector<int> factorial(int N){
        vector<int> ans;
        ans.push_back(1);
        for(int i = 2; i <= N; i++){
            int carry = 0;
            for(int j = 0; j < ans.size(); j++){
                int prod = ans[j]*i + carry;
                ans[j] = prod%10;
                carry = prod/10;
            }
            while(carry){
                ans.push_back(carry%10);
                carry /= 10;
            }
        }
        reverse(ans.begin(),ans.end());
        return ans;
    }
};
```
