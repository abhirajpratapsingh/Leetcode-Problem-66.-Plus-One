
# Intuition
<!-- Describe your first thoughts on how to solve this problem. -->
- The problem seems to involve adding one to a given integer represented as an array of digits. The array may contain leading zeros, and the goal is to return the result as a new array.

---

![Screenshot (47).png](https://assets.leetcode.com/users/images/ab79d6a6-0341-40be-8334-ffb064956f23_1704901894.8121877.png)


---


# Approach
<!-- Describe your approach to solving the problem. -->
1. Start iterating from the rightmost digit of the array.
2. Increment the rightmost digit by 1.
3. If the incremented digit becomes 10, set it to 0 and move to the next left digit. Continue this process until a digit is found that is less than 10.
4. If all digits are incremented and become 10, a new digit 1 should be added at the beginning of the array.
5. Return the modified array.

---


# Complexity

---


- Time complexity:
<!-- Add your time complexity here, e.g. $$O(n)$$ -->
- **Time complexity: The time complexity is O(n),** where n is the number of digits in the array. In the worst case, the algorithm iterates through all the digits once.

---


- Space complexity:
<!-- Add your space complexity here, e.g. $$O(n)$$ -->
- **Space complexity: The space complexity is O(1),** as the algorithm uses only a constant amount of extra space regardless of the input size. The modification is done in place on the given vector.

---


# Code
```
class Solution {
public:
    vector<int> plusOne(vector<int>& digits) 
    {
         int n = digits.size();
        for(int i = n-1; i >= 0; i--){
            if(i == n-1)
                digits[i]++;
            if(digits[i] == 10){
                digits[i] = 0;
                if(i != 0){
                    digits[i-1]++;
                }
                else{
                    digits.push_back(0);
                    digits[i] = 1;
                }
            }
        }
        return digits;
    }
};
```

