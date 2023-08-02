# leetcode_assignment
Transpose Matrix--------------------------------------------
Given a 2D integer array matrix, return the transpose of matrix.

The transpose of a matrix is the matrix flipped over its main diagonal, switching the matrix's row and column indices.
Example 1:

Input: matrix = [[1,2,3],[4,5,6],[7,8,9]]
Output: [[1,4,7],[2,5,8],[3,6,9]]
Example 2:

Input: matrix = [[1,2,3],[4,5,6]]
Output: [[1,4],[2,5],[3,6]]

OUTPUT:
class Solution {
    public int[][] transpose(int[][] mat) {
        int matrix[][]=new int[mat[0].length][mat.length];
        for(int i=0;i<mat.length;i++){
            for(int j=0;j<mat[i].length;j++){
                matrix[j][i]=mat[i][j];
            }
        }
        return matrix;
    }
}


Richest Customer Wealth-----------------------------------------------------
You are given an m x n integer grid accounts where accounts[i][j] is the amount of money the i​​​​​​​​​​​th​​​​ customer has in the j​​​​​​​​​​​th​​​​ bank. Return the wealth that the richest customer has.
A customer's wealth is the amount of money they have in all their bank accounts. The richest customer is the customer that has the maximum wealth.
Input: accounts = [[1,2,3],[3,2,1]]
Output: 6
Explanation:
1st customer has wealth = 1 + 2 + 3 = 6
2nd customer has wealth = 3 + 2 + 1 = 6
Both customers are considered the richest with a wealth of 6 each, so return 6.
Input: accounts = [[1,5],[7,3],[3,5]]
Output: 10
Explanation: 
1st customer has wealth = 6
2nd customer has wealth = 10 
3rd customer has wealth = 8
The 2nd customer is the richest with a wealth of 10.
Input: accounts = [[2,8,7],[7,1,3],[1,9,5]]
Output: 17

class Solution {
    public int maximumWealth(int[][] accounts) {
        int sum=0;
        for(int i=0;i<accounts.length;i++){
            int temp=0;
            for(int j=0;j<accounts[i].length;j++){
                temp+=accounts[i][j];
            }
            sum=Math.max(sum,temp);
        }
        return sum;
    }
}

Toeplitz Matrix---------------------------------------------------------------------------
Given an m x n matrix, return true if the matrix is Toeplitz. Otherwise, return false.

A matrix is Toeplitz if every diagonal from top-left to bottom-right has the same elements.

 Input: matrix = [[1,2,3,4],[5,1,2,3],[9,5,1,2]]
Output: true
Explanation:
In the above grid, the diagonals are:
"[9]", "[5, 5]", "[1, 1, 1]", "[2, 2, 2]", "[3, 3]", "[4]".
In each diagonal all elements are the same, so the answer is True.
Input: matrix = [[1,2],[2,2]]
Output: false
Explanation:
The diagonal "[1, 2]" has different elements.

class Solution {
    public boolean isToeplitzMatrix(int[][] matrix) {
        for(int i=0;i<matrix.length-1;i++){
            for(int j=0;j<matrix[i].length-1;j++){
                if(matrix[i][j]!=matrix[i+1][j+1]){
                    return false;
                }
            }
        }
        return true;
    }
}

Matrix Diagonal Sum--------------------------------------------------------------------------------
Given a square matrix mat, return the sum of the matrix diagonals.
Only include the sum of all the elements on the primary diagonal and all the elements on the secondary diagonal that are not part of the primary diagonal
Input: mat = [[1,2,3],
              [4,5,6],
              [7,8,9]]
Output: 25
Explanation: Diagonals sum: 1 + 5 + 9 + 3 + 7 = 25
Notice that element mat[1][1] = 5 is counted only once.


 class Solution {
    public int diagonalSum(int[][] mat) {
        int sum=0;
        if(mat.length%2!=0){
        for(int i=0;i<mat.length;i++){
           if(i==mat.length/2){
               sum+=mat[i][i];
           }  
           else{
               sum+=mat[i][i]+mat[i][mat.length-i-1];
           }
        }
    }
    else{
        for(int i=0;i<mat.length;i++){
            sum+=mat[i][i]+mat[i][mat.length-i-1];
        }
    }
    return sum;
}
}

Count Negative Numbers in a Sorted Matrix------------------------------------------------------------------

Given a m x n matrix grid which is sorted in non-increasing order both row-wise and column-wise, return the number of negative numbers in grid.
Input: grid = [[4,3,2,-1],[3,2,1,-1],[1,1,-1,-2],[-1,-1,-2,-3]]
Output: 8
Explanation: There are 8 negatives number in the matrix.
Input: grid = [[3,2],[1,0]]
Output: 0

class Solution {
    public int countNegatives(int[][] g) {
        int count=0;
        for(int i=0;i<g.length;i++){
            for(int j=0;j<g[i].length;j++){
                if(g[i][j]<0){
                    count++;
                }
            }
        }
        return count;
    }
}
