# EX 3E Generate Permutations using Backtracking  Approach.

## DATE: 02/08/2026

## AIM:

To write a Java program to for given constraints. Given an array nums of distinct integers, return all the possible Permutation. You can return the answer in any order.

Example 1:

Input: nums = [1,2,3]

Output: [[1,2,3],[1,3,2],[2,1,3],[2,3,1],[3,1,2],[3,2,1]]

## Algorithm

1. Start and read the array of numbers.

2. Use a recursive backtracking function to build permutations.

3. At each step, add an unused element to the current list.

4. When the current list size equals the array length, add it to the result.

5. Backtrack by removing the last element and continue until all permutations are generated.

## Program:

Program to implement Reverse a String

Developed by: KEERTHIVASAN S

Register Number: 212223220046 

```
import java.util.*;

public class Solution {

    public List<List<Integer>> permute(int[] nums) {
        List<List<Integer>> ans = new ArrayList<>();
        backtrack(new ArrayList<>(), ans, nums);
        return ans;
    }

    public void backtrack(List<Integer> curr, List<List<Integer>> ans, int[] nums) {
        if (curr.size() == nums.length) {
            ans.add(new ArrayList<>(curr));
            return;
        }
        for (int num : nums) {
            if (!curr.contains(num)) {
                curr.add(num);
                backtrack(curr, ans, nums);
                curr.remove(curr.size() - 1);
            }
        }
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String inputLine = scanner.nextLine().trim();

        // ✅ Correct way to remove brackets
        inputLine = inputLine.replaceAll("\\[|\\]", "");
        String[] parts = inputLine.split(",");

        int[] nums = new int[parts.length];
        for (int i = 0; i < parts.length; i++) {
            nums[i] = Integer.parseInt(parts[i].trim());
        }

        Solution solution = new Solution();
        List<List<Integer>> permutations = solution.permute(nums);
        System.out.println(permutations);
        scanner.close();
    }
}

```

## Output:

<img width="644" height="591" alt="m13-t4op" src="https://github.com/user-attachments/assets/d5deafdc-9567-42e9-a17f-16d7074b841e" />

## Result:
Thus, the program successfully implemented and the expected output is verified.
