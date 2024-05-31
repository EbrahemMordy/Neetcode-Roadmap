## Using Sort

Time Complexity: O(N) for Sort Function

Space Complexity: O(1)

```cpp
class Solution {
public:
    bool containsDuplicate(vector<int> &nums) {
        sort(nums.begin(), nums.end());
        for (int i = 0; i + 1 < nums.size(); i++) {
            if (nums[i] == nums[i + 1]) {
                return true;
            }
        }
        return false;
    }
};
```

## Using Hash 'Map'

Time Complexity: O(N) for Sort Function

Space Complexity: O(N) if all values are distinct

```cpp
class Solution {
public:
    bool containsDuplicate(vector<int> &nums) {
        map<int, int> map1;
        for (int i = 0; i < nums.size(); i++) {
            map1[nums[i]]++;
            if (map1[nums[i]] >= 2)
                return true;
        }
        return false;
    }
};
```

For More Details about Map see this course

[STL Course In arabic](https://youtube.com/playlist?list=PLCInYL3l2AainAE4Xq2kdNGDfG0bys2xp&si=mnOd6z_4jd5ONl9i)
