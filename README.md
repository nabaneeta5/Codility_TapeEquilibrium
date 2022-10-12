# Codility_TapeEquilibrium
Minimize the value |(A[0] + ... + A[P-1]) - (A[P] + ... + A[N-1])|.

# Task description
A non-empty array A consisting of N integers is given. Array A represents numbers on a tape.

Any integer P, such that 0 < P < N, splits this tape into two non-empty parts: A[0], A[1], ..., A[P − 1] and A[P], A[P + 1], ..., A[N − 1].

The difference between the two parts is the value of: |(A[0] + A[1] + ... + A[P − 1]) − (A[P] + A[P + 1] + ... + A[N − 1])|

In other words, it is the absolute difference between the sum of the first part and the sum of the second part.

# Link Details
[trainingDHY6YG-6E8](https://app.codility.com/demo/results/trainingDHY6YG-6E8/)

# Programming Language
Java SE 11

# Solution Code

```
class Solution {
    public int solution(int[] A) {
        // write your code in Java SE 11

        int sumPre = A[0];
        int sumPost = 0;
        for (int i = 1; i < A.length; i++) {
            sumPost += A[i];
        }
        int difMin = Math.abs(sumPost - sumPre);
        int tempSub = 0;
        for (int i = 1; i < A.length - 1; i++) {
            sumPre += A[i];
            sumPost -= A[i];
            tempSub = Math.abs(sumPost - sumPre);
            if (tempSub < difMin) {
                difMin = tempSub;
            }
        }
        return difMin;                                  
    }
}


```


