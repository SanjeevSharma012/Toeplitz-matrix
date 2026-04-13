📘 Toeplitz Matrix Checker
🔹 Problem Statement

A Toeplitz matrix (also known as a diagonal-constant matrix) is a matrix in which every diagonal from top-left to bottom-right contains the same element.

Given a 2D matrix mat, determine whether it is a Toeplitz matrix or not.

🔹 Function Requirement

Implement the function:

boolean isToeplitz(int[][] mat)
✅ Return:
true → if the matrix is Toeplitz
false → otherwise
🔹 Examples
Example 1
Input:
1  2  3  4
5  1  2  3
9  5  1  2

Output:
true
Example 2
Input:
1  2
2  2

Output:
false
🔹 Approach

Instead of checking each diagonal separately, we use an optimized approach:

👉 Compare every element with its top-left neighbor

💡 Key Idea:

For every element mat[i][j]:

mat[i][j] == mat[i-1][j-1]

If any comparison fails → matrix is not Toeplitz

🔹 Algorithm Steps
Start from row 1 and column 1
Traverse the matrix
For each element:
Compare with top-left element
If mismatch found → return false
If no mismatch → return true
🔹 Code Implementation (Java)
class Solution {
    public boolean isToeplitz(int[][] mat) {
        for(int i = 1; i < mat.length; i++){
            for(int j = 1; j < mat[0].length; j++){
                if(mat[i][j] != mat[i-1][j-1]){
                    return false;
                }
            }
        }
        return true;
    }
}
🔹 Time & Space Complexity
⏱ Time Complexity: O(m × n)
🧠 Space Complexity: O(1) (no extra space used)
🔹 Edge Cases to Consider
Single row matrix → always Toeplitz
Single column matrix → always Toeplitz
1×1 matrix → always Toeplitz
Negative numbers → valid
Rectangular matrix (not square) → valid
🔹 Key Takeaway

👉 You don’t need to traverse diagonals separately
👉 Just ensure:
Each element = its top-left neighbor

Author
Sanjeev Sharma
