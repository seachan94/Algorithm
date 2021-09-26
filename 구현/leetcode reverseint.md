## URL
    https://leetcode.com/problems/reverse-integer/submissions/
## CODE

    class Solution {
    public:
        int reverse(int x) {
            bool flag = false;
            if (x <= -2147483648 || x >=  2147483647)
                return 0;

            if (x <0){
                flag = true;
                x = x*-1;
            }
            long long ans = 0;
            while(x>0){
                ans=ans*10+x%10;
                x/=10;
            }

            if (ans >=  2147483647)
                return 0;

            if(flag){
                return -1*ans;
            }
            return ans;
        }
    };
