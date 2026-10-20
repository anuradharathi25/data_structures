## 01. Replace with Adjacent Multiplication

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/replace-with-adjacent-multiplication/1)

### Problem Description

**Task:** Given an array arr[], replace every element with the product of itself and its adjacent elements.
For index i: arr[i] = arr[i-1] * arr[i] * arr[i+1]
Assume the previous element of the first element and the next element of the last element as 1.

#### Examples

##### Example 1

- **Input:**
```text
arr[] = [2, 4, 5]
```
- **Output:**
```text
[8, 40, 20] For index i = 0, arr[0] = 1 * arr[0] * arr[1] = 1 * 2 * 4 = 8 For index i = 1, arr[1] = arr[0] * arr[1] * arr[2] = 2 * 4 * 5 = 40 For index i = 2, arr[2] = arr[1] * arr[2] * 1 = 4 * 5 * 1 = 20 Thus, the updated array becomes [8, 40, 20].
```

##### Example 2

- **Input:**
```text
arr[] = [2, 5, 7, 8, 3]Output: [10, 70, 280, 168, 24]Explanation:For index i = 0, arr[0] = 1 * arr[0] * arr[1] = 1 * 2 * 5 = 10 For index i = 1, arr[1] = arr[0] * arr[1] * arr[2] = 2 * 5 * 7 = 70 For index i = 2, arr[2] = arr[1] * arr[2] * arr[3] = 5 * 7 * 8 = 280 For index i = 3, arr[3] = arr[2] * arr[3] * arr[4] = 7 * 8 * 3 = 168 For index i = 4, arr[4] = arr[3] * arr[4] * 1 = 8 * 3 * 1 = 24Thus, the updated array becomes [10, 70, 280, 168, 24].
```

#### Constraints

- **1.** `1 ≤ arr[i] ≤ 10³¹ ≤ arr.size() ≤ 10⁵`

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (C++)

- **Submitted:** 2026-10-20 16:24:41
- **Status:** Correct
- **Marks:** 2

```cpp
class Solution {
  public:
    void updateArray(vector<int>& arr) {
        // code here
        int n=arr.size();
        vector<int> temp(n);
            for(int i=0;i<n;i++){
            int prev = (i == 0) ? 1 : arr[i - 1];
            int next = (i == n - 1) ? 1 : arr[i + 1];
            temp[i] = prev * arr[i] * next;
            }
        arr=temp;
    }
};
```

*Generated on: 10/20/2026, 4:25:52 PM*