## Using Frequancy Array

Time Complexity: O(N) For Loop Time

Space Complexity: O(26)

```cpp
class Solution {
public:
    int getindex(char x) {
        return x - 'a';
    }

    bool isAnagram(string s, string t) {
        vector<int> freqFromS(26);
        for (int i = 0; i < s.size(); i++) {
            freqFromS[getindex(s[i])]++;
        }
        vector<int> freqFromT(26);
        for (int i = 0; i < t.size(); i++) {
            freqFromT[getindex(t[i])]++;
        }
        for (int i = 0; i < 26; i++) {
            if (freqFromS[i] != freqFromT[i]) {
                return false;
            }
        }
        return true;
    }
};
```

## Using Sort

Time Complexity: O(N) for Sort Function

Space Complexity: O(1)

```cpp
class Solution {
public:
    bool isAnagram(string s, string t) {
        std::sort(s.begin(), s.end());
        std::sort(t.begin(), t.end());
        if (s == t)
            return true;
        return false;
    }
};
```

For More Details about Frequancy Array See this video

[Video For Dr/Mohamed Afifi](https://youtu.be/kQGTjql8WjI?si=WxhKglK7D6E0Py0B)
