## URL
    
    https://leetcode.com/submissions/detail/561833077/?from=explore&item_id=3989
    
## PYTHON CODE

    class Solution(object):
        def numUniqueEmails(self, emails):
            result = set()

            for email in emails:
                divided = email.split('@')
                user_ = divided[0]
                domain_ = divided[1]
                localname = self.check_user(user_)
                result.add(localname+'@'+domain_)

            return len(result)
        def check_user(self,user):

            user = user.replace('.','')
            return user.split('+')[0]

## CPP CODE

    class Solution {
    public:
        int numUniqueEmails(vector<string>& emails) {
            unordered_set<string> s;
            for(int i=0;i<emails.size();i++){

                int find_idx = emails[i].find('@');
                string user = emails[i].substr(0,find_idx);
                string localname = "";
                for(int j=0;j<user.size();j++){
                    if(user[j] == '.'){
                        continue;
                    }
                    else if(user[j]=='+'){
                        s.insert(localname+"@"+emails[i].substr(find_idx,emails[i].size()))   ;
                        break;
                    }
                    else{
                        localname+=user[j];
                    }
                    if (j == user.size()-1){
                         s.insert(localname+"@"+emails[i].substr(find_idx,emails[i].size()))   ;
                    }
                }

            }
            return s.size();
        }
    };
  
