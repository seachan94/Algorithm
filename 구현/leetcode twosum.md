### URL
    https://leetcode.com/problems/two-sum/submissions/
### Code
    class Solution {
    public:
        vector<int> twoSum(vector<int>& nums, int target) {
            vector<int> ans;
            unordered_map<int,int> m;
            for(int i=0;i<nums.size();i++){
                if(m.find(nums[i])!=m.end()){
                    ans.push_back(m[i]);
                    ans.push_back(i);
                    return ans;
                }
                m[target-nums[i]] =i;
            }
            return ans;
        }
    };


