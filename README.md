# Daily-Leetcode-problem-solution7

PROBLEM

Given an integer n, find a sequence that satisfies all of the following:

The integer 1 occurs once in the sequence.
Each integer between 2 and n occurs twice in the sequence.
For every integer i between 2 and n, the distance between the two occurrences of i is exactly i.
The distance between two numbers on the sequence, a[i] and a[j], is the absolute difference of their indices, |j - i|.

Return the lexicographically largest sequence. It is guaranteed that under the given constraints, there is always a solution.

A sequence a is lexicographically larger than a sequence b (of the same length) if in the first position where a and b differ, sequence a has a number greater than the corresponding number in b. For example, [0,1,9,0] is lexicographically larger than [0,1,5,6] because the first position they differ is at the third number, and 9 is greater than 5.

 Intuition
 
Backtracking Approach:

Since we need to construct the sequence in a way that it satisfies the given constraints and is lexicographically largest, a backtracking approach is suitable.
We will start from the largest possible number (n) and try to place it in the sequence first. This ensures that our sequence remains lexicographically largest.
If placing a number leads to a valid configuration, we proceed; otherwise, we backtrack.

Approach

Constraints to Follow:

The integer 1 appears once in the sequence.
Each number between 2 and n appears twice, and their indices should be i apart.
We maintain a used set to track which numbers have been placed.
Recursive Placement Strategy:

We iterate through the available positions in the sequence.
If the current number x can be placed at index i and also at index i + x (if x > 1), we place it and recurse.
If we cannot place x, we move to a smaller number.
Lexicographically Largest Order:

Since we need the lexicographically largest sequence, we start placing numbers from n down to 1.

"result" stores the sequence of size 2 * n - 1, initialized with 0s.
"used" keeps track of which numbers have been placed.
backtrack(idx) recursively fills the sequence:

Skips already filled positions.
Tries to place numbers from n down to 1 (to maintain lexicographically largest order).
Checks if num can be placed at idx and idx + num.
If placing the number leads to a valid configuration, the function returns true, else backtracks.

Complexity

Time complexity:
O(n!)

Space complexity:
O(n)
