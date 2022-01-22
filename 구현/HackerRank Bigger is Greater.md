## introduce
    풀이 방버 : next_permutation
- 즉 비교해야 할 단어의 뒤에 위치하 단어드 중 비교 대상군 보다 큰 집합 중 가장 작은 단어르 찾아 비교군고 바꾸고 나머지 오름 차순 해주면 됨
- next_permutation
   

## PYTHON CODE

    def biggerIsGreater(w):
        result = ""
        idx = len(w)-1
        for i in range(idx,-1,-1):
            check = -1
            for j in range(idx,i,-1):

                if w[i]< w[j]:
                    if check ==-1:
                        check = j
                    elif w[check]>w[j]:
                        check = j
            if check !=-1:
                arr = [x for x in w]
                a = arr[i]
                b = arr[check]
                arr[check] = a
                arr[i] = b
                for x in arr[0:i+1]:
                    result+=x
                for x in sorted(arr[i+1:]):
                    result+=x
                break
        if result == "":
            return "no answer"
        return result


