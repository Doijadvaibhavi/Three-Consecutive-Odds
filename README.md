# Three-Consecutive-Odds

Given an integer array arr, return true if there are three consecutive odd numbers in the array. Otherwise, return false.
 
Example 1:

Input: arr = [2,6,4,1]
Output: false
Explanation: There are no three consecutive odds.
Example 2:

Input: arr = [1,2,34,3,4,5,7,23,12]
Output: true
Explanation: [5,7,23] are three consecutive odds.
 
Constraints:

1 <= arr.length <= 1000
1 <= arr[i] <= 1000


# SOLUTION

# Intuition
The problem requires checking if there are any three consecutive odd numbers in the given array. This can be solved by iterating through the array and maintaining a count of consecutive odd numbers. When the count reaches three, we return true. If we encounter an even number, we reset the count.

# Approach
Initialize a counter count to 0.
Iterate through each element in the array.
For each element, check if it is odd:
If it is odd and count is less than 2, increment the count.
If it is odd and count is 2, return true since we have found three consecutive odd numbers.
If it is even, reset the count to 0.
If the loop completes without finding three consecutive odd numbers, return false.
Complexity
Time Complexity: (O(n)), where (n) is the length of the array. This is because we iterate through the array once.
Space Complexity: (O(1)). No extra space is required except for a few variables.
Step-by-Step Explanation

# Initialization:

We start with a counter count set to 0. This counter will keep track of the number of consecutive odd numbers encountered.
count = 0
Iteration Through the Array:

We iterate through each element in the array arr.
For each element, we check if it is odd (num % 2 != 0).
If the element is odd, we increment the counter count.
If the element is even, we reset the counter count to 0.
If the counter count reaches 3, we return true as we have found three consecutive odd numbers.
If we finish iterating through the array without the counter count reaching 3, we return false.
Example
Input: arr = [1, 2, 34, 3, 4, 5, 7, 23, 12]

Output: true (Explanation: [5, 7, 23] are three consecutive odd numbers)



# JAVA CODE

class Solution {

    public boolean threeConsecutiveOdds(int[] arr) {
    
        int count = 0;  

        for (int i = 0; i < arr.length; i++) {  
        
            if (arr[i] % 2 != 0) {  
            
                count++;  
                
                if (count == 3) {
                
                    return true;
                    
                }
            } else {  
            
                count = 0;
                
            }
        }

        return false;  
    }
}
