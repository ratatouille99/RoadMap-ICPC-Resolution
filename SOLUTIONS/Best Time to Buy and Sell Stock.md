# [Best Time to Buy and Sell Stock](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/)
```c++
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int sumMax = 0, sumAct = prices[0];

        for(int i = 1; i < prices.size(); i++){
            int aux = prices[i] - sumAct;

            if(sumMax < aux) sumMax = aux;

            if(aux < 0) sumAct = prices[i];
        }

        return sumMax;
    }
};
```
