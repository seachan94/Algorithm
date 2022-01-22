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


