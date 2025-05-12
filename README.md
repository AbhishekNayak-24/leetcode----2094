# leetcode----2094
Finding 3-Digit Even Numbers
//code in java
import java.util.ArrayList;
import java.util.HashSet;
import java.util.List;
import java.util.Set;

class Solution {
    public int[] findEvenNumbers(int[] digits) {
        Set<Integer> result = new HashSet<>();
        for (int i = 0; i < digits.length; i++) {
            for (int j = 0; j < digits.length; j++) {
                for (int k = 0; k < digits.length; k++) {
                    if (i != j && i != k && j != k) {
                        int num = digits[i] * 100 + digits[j] * 10 + digits[k];
                        if (num % 2 == 0 && num >= 100) {
                            result.add(num);
                        }
                    }
                }
            }
        }
        List<Integer> sortedResult = new ArrayList<>(result);
        sortedResult.sort(null);
        int[] arr = new int[sortedResult.size()];
        for (int i = 0; i < sortedResult.size(); i++) {
            arr[i] = sortedResult.get(i);
        }
        return arr;
    }
}
