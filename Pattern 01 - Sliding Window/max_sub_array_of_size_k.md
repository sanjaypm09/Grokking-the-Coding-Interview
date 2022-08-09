# Maximum Sum Subarray of Size K 
### Difficulty: Easy
### Pattern: Sliding Window
### Tags: 
### Company Tags: 

<br />

### Problem Statement:
#### Given an array of positive numbers and a positive number ‘k,’ find the maximum sum of any contiguous subarray of size ‘k’.

<br />
Example 1:

Input: [2, 1, 5, 1, 3, 2], k=3 <br />
Output: 9 <br />
Explanation: Subarray with maximum sum is [5, 1, 3].

<br />

Example 2:

Input: [2, 3, 4, 1, 5], k=2 <br />
Output: 7 <br />
Explanation: Subarray with maximum sum is [3, 4].

```python
def max_sub_array_of_size_k(k, arr):
    start = 0  # Pointer to Start of the Window
    win_sum = 0  # Window Sum
    max_sum = float("-inf")  # Maximum Sum

    for end in range(len(arr)):
        win_sum += arr[end]  # Add next element to the window

        # Slide the window if we've reached max window size of 'k'
        if end >= k - 1:
            max_sum = max(max_sum, win_sum)
            win_sum -= arr[start]  # Subtract the element to be removed from the window
            start += 1  # Slide the window by one

    return max_sum


if __name__ == "__main__":
    print("Maximum sum of a subarray of size K: " + str(max_sub_array_of_size_k(3, [2, 1, 5, 1, 3, 2])))
    print("Maximum sum of a subarray of size K: " + str(max_sub_array_of_size_k(2, [2, 3, 4, 1, 5])))
  ```
  ### Complexity Analysis:
  * ### Time Complexity: O(N)
  * ### Space Compelxity: O(1)

  Where N is the number of elements in the array.
