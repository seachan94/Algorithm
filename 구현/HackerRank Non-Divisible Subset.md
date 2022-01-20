## URL

    https://www.hackerrank.com/challenges/non-divisible-subset/problem?isFullScreen=true
    

## Language
    Kotlin

## CODE
    fun nonDivisibleSubset(k: Int, s: Array<Int>): Int {
        // Write your code here
        var array = IntArray(k)
        var result = 0
        for(value in s){ array[value%k]+=1 }

        if(array[0] >=1){result +=1}

        if(k%2 == 0 && array[k/2]>0){ array[k/2]= 1 }

        for(i in (1..k/2)){

            if(array[i]<array[k-i]){
                result+=array[k-i]
            }else{
                result+=array[i]
            }
        }
        return result
    }
