# 1. Two Sum

https://leetcode.com/problems/two-sum/

```c++
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        vector<int> res;
        unordered_map<int, int> map; 
        for(int i = 0; i < nums.size(); i++) {
            // 寻找当前数字是否存在，若不存在就将该数的索引与互补数字压入
            if(map.find(nums[i]) == map.end()) {
                map[target - nums[i]] = i;
            }
            // 如果当前数字存在，即说明互补数字在之前存在过，
            // 可直接获取该索引值，并返回
            else {
                res.push_back(i);
                res.push_back(map[nums[i]]);
                break;
            }
        }
        return res;
    }
};
```
