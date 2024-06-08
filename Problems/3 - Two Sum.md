## Using Brute Force

Time Complexity: O(N<sup>2</sup>) For Nested Loop Time

Space Complexity: O(1)

```cpp
class Solution {
public:
    vector<int> twoSum(vector<int> &nums, int target) {
        for (int i = 0; i < nums.size(); i++) {
            for (int j = i + 1; j < nums.size(); j++) {
                //nums[i]+nums[j]=target;
                if (nums[i] + nums[j] == target) {
                    return {i, j};
                }
            }
        }
        return {-1, -1};
    }
};
```

## Using Hashing 'Map'

Time Complexity: O(N) for Loop Time

Space Complexity: O(N) if all values are distinct

```cpp
class Solution {
public:
    vector<int> twoSum(vector<int> &nums, int target) {
        map<int, int> seen;
        for (int i = 0; i < nums.size(); i++) {
            //x=target - nums[i];
            int x = target - nums[i];
            if (seen.find(x) != seen.end()) {
                return {i, seen[x]};
            }
            seen[nums[i]] = i;
        }
        return {-1, -1};
    }
};
```
