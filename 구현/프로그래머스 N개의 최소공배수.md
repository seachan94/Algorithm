## CODE

    def solution(arr):
        answer = 0

        answer= max(arr)
        maxnum = max(arr)
        flag = False
        while(flag ==False):
            flag = True
            for num in arr:
                if answer % num != 0:
                    flag = False
                    break
            if flag == False:
                answer+=maxnum
        return answer
