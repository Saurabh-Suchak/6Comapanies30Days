# Max Points on a Line

link - https://leetcode.com/problems/minimum-consecutive-cards-to-pick-up/description/

### Problem Statement - 
You are given an integer array cards where cards[i] represents the value of the ith card. A pair of cards are matching if the cards have the same value.

Return the minimum number of consecutive cards you have to pick up to have a pair of matching cards among the picked cards. If it is impossible to have matching cards, return -1.

### Sample Input
```
cards = [3,4,2,3,4,7]
```
### Sample Output
```
 4
Explanation: We can pick up the cards [3,4,2,3] which contain a matching pair of cards with value 3. Note that picking up the cards [4,2,3,4] is also optimal.
```

### Solution

```cpp
class Solution {
public:
    int minimumCardPickup(vector<int>& nums) {
        unordered_map<int,int>mp;
        int mini=INT_MAX;
        
        for(int i=0;i<nums.size();i++){
            
            if(mp.find(nums[i]) != mp.end()){mini=min(mini,i-mp[nums[i]]+1);}
            
            mp[nums[i]]=i;  
        }
        if(mini==INT_MAX)return -1;
        return mini;
        
        
    }
};

```