## 01. Check Sorted Array

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/check-if-an-array-is-sorted0701/1)

### Problem Description

**Task:** Given an array arr[], check whether it is sorted in non-decreasing order. Return true if it is sorted otherwise false.Examples:Input: arr[] = [10, 20, 30, 40, 50]

#### Examples

##### Example 1

- **Output:**
```text
false
```
- **Explanation:** The given array is not sorted.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (2)

#### Solution 1 (C++)

- **Submitted:** 2026-10-20 14:51:58
- **Status:** Correct
- **Marks:** 0

```cpp
class Solution {
  public:
    bool isSorted(vector<int>& arr) {
        // code here
    if (arr.size()<=1){
    return true;
    }
        
        for(int i=1; i<arr.size(); i++){
            
           if (arr[i - 1] > arr[i]){
        return false;
           }
        }
        return true;
        
    }
};
```

#### Solution 2 (C++)

- **Submitted:** 2026-10-20 14:51:11
- **Status:** Correct
- **Marks:** 2

```cpp
class Solution {
  public:
    bool isSorted(vector<int>& arr) {
        // code here
    if (arr.size()<=1){
    return true;
    }
        
        for(int i=1; i<arr.size(); i++){
            
        if (arr[i - 1] > arr[i]){
        return false;
        }
        }
        return true;
        
    }
};
```
\*let array size=5
i=1; i<5
if (arr[0]>arr[1])--false
checks till i<5*\

*Generated on: 10/20/2026, 3:53:21 PM*
