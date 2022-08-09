# Smallest Subarray With a Greater Sum
### Difficulty: Easy
### Pattern: Sliding Window
### Tags: 
### Company Tags: 

<br />

### Problem Statement:
#### Given an array of positive integers and a number ‘S,’ find the length of the smallest contiguous subarray whose sum is greater than or equal to ‘S’. Return 0 if no such subarray exists.

<br />

Example 1:

Input: [2, 1, 5, 2, 3, 2], S=7 <br />
Output: 2 <br />
Explanation: The smallest subarray with a sum greater than or equal to ‘7’ is [5, 2].

<br />

Example 2:

Input: [2, 1, 5, 2, 8], S=7 <br />
Output: 1 <br />
Explanation: The smallest subarray with a sum greater than or equal to ‘7’ is [8].

<br />

Example 3:

Input: [3, 4, 1, 1, 6], S=8 <br />
Output: 3 <br />
Explanation: Smallest subarrays with a sum greater than or equal to ‘8’ are [3, 4, 1] or [1, 1, 6].

<br />

```python
def smallest_subarray_sum(s, arr):
  start = 0  # Pointer to the Start of the Window
  curr_sum = 0  # Window Sum
  min_len = float("inf")  # Minimum length of sub array

  for end in range(len(arr)):
    curr_sum += arr[end]  # Add next element to the window

    # Shrink the window size until window sum < 's'
    while curr_sum >= s:  
      min_len = min(min_len, end - start + 1)  # Check if current window length is the smallest
      curr_sum -= arr[start]  # Subtract the element to be removed from the window
      start += 1  # Slide the window by one

  return 0 if min_len == float("inf") else min_len  # Return 0 if no such sub array exists, otherwise return Minumum subarray length

if __name__ == "__main__":
  print("Smallest subarray length: " + str(smallest_subarray_sum(7, [2, 1, 5, 2, 3, 2])))
  print("Smallest subarray length: " + str(smallest_subarray_sum(8, [3, 4, 1, 1, 6])))
  print("Smallest subarray length: " + str(smallest_subarray_sum(8, [2, 1, 5, 2, 3, 2])))
  ```
  ### Complexity Analysis:
  * ### Time Complexity: O(N)
  * ### Space Compelxity: O(1)

  Where N is the number of elements in the array.
