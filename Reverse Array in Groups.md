## 01. Reverse Array in Groups

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/reverse-array-in-groups0255/1)

### Problem Description

**Task:** Given an integer array arr[] and an integer k, reverse every consecutive group of k elements. If fewer than k elements remain at the end, reverse all of them.Examples:Input: arr[] = [1, 2, 3, 4, 5], k = 3Output: [3, 2, 1, 5, 4]

#### Examples

##### Example 1

- **Explanation:** First group consists of elements 1, 2, 3. Second group consists of 4, 5.Input: arr[] = [5, 6, 8, 9], k = 5Output: [9, 8, 6, 5]Explnation: Since k is greater than the number of remaining elements, the entire array is reversed.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (C++)

- **Submitted:** 2026-10-20 18:45:35
- **Status:** Correct
- **Marks:** 4

```cpp
class Solution {
  public:
    void reverseInGroups(vector<int> &arr, int k) {
        // code here
        int n= arr.size();
        for (int i = 0; i < n; i += k) {
                int left = i;
                int right = min(i + k - 1, n - 1);
                while (left < right)  {
                    swap(arr[left++], arr[right--]);
                }
        }
    }
};


/*let n=5,k=3
i=0; 0<4; --left=0, right=min(2,4)
while(0<2)
swap(arr[0],arr[2])
swap(arr[1],arr[1])
value of left=right out of while loop

i=3; 3<4; --left=3, right=min(5,4)
while(3<4)
swap(arr[3],arr[4])
value of left=4, right=3---out of while loop
*/
```

*Generated on: 10/20/2026, 6:46:27 PM*