# [Find the duplicate number](https://leetcode.com/problems/find-the-duplicate-number/solutions/)
```c++
class Solution {
public:
    int findDuplicate(vector<int>& nums) {
        int hare = nums[nums[nums[0]]], tortoise = nums[nums[0]];

        while(hare != tortoise){
            tortoise = nums[tortoise];
            hare = nums[nums[hare]];
        }

        tortoise = nums[0];

        while(hare != tortoise){
            tortoise = nums[tortoise];
            hare = nums[hare];
        }

        return tortoise;
    }
};
```
