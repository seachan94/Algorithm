## CODE
    def solution(s):    
        ans = ''
        for idx in range(len(s)):
            if idx ==0:
                ans+=s[idx].upper()
            elif s[idx-1] == ' ':
                ans+=s[idx].upper()
            else:
                ans+=s[idx].lower()
        print(ans)
        return ans
