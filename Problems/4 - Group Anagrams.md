## Using Brute Force

Time Complexity: O(N<sup>2</sup>) For Nested Loop Time

Space Complexity: O(N) if all values are distinct

```cpp
class Solution {
public:
    bool CheckAnagram(string a, string b) {
        return a == b;
    }

    vector<vector<string>> groupAnagrams(vector<string> &strs) {
        vector<vector<string>> ans;
        vector<string> sorted(strs.size());
        for (int i = 0; i < strs.size(); i++) {
            sorted[i] = strs[i];
            std::sort(sorted[i].begin(), sorted[i].end());
        }
        for (int i = 0; i < strs.size(); i++) {
            if (strs[i] == "Z")
                continue;
            vector<string> currentGroup;
            currentGroup.push_back(strs[i]);
            for (int j = i + 1; j < strs.size(); j++) {
                if (CheckAnagram(sorted[i], sorted[j])) {
                    currentGroup.push_back(strs[j]);
                    strs[j] = "Z";
                }
            }
            ans.push_back(currentGroup);
        }
        return ans;
    }
};
```

## Using Hashing 'Map'

Time Complexity: O(N) for Loop Time

Space Complexity: O(N) if all values are distinct

```cpp
class Solution {
public:
    vector<vector<string>> groupAnagrams(vector<string> &strs) {
        map<string, vector<string>> groups;
        for (auto i: strs) {
            string key = i;
            std::sort(key.begin(), key.end());
            groups[key].push_back(i);
        }
        vector<vector<string>> ans;
        for (auto i: groups) {
            ans.push_back(i.second);
        }
        return ans;
    }
};
```
