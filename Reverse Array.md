## 01. Reverse Array

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/reverse-an-array/1)

### Problem Description

**Task:** You are given an array of integers arr[]. You have to reverse the given array.

> **Note:** Modify the array in place.

#### Examples

##### Example 1

- **Input:**
```text
arr = [1, 4, 3, 2, 6, 5]
```
- **Output:**
```text
[5, 6, 2, 3, 4, 1]Explanation: The elements of the array are [1, 4, 3, 2, 6, 5]. After reversing the array, the first element goes to the last position, the second element goes to the second last position and so on. Hence, the answer is [5, 6, 2, 3, 4, 1].
```

##### Example 2

- **Input:**
```text
arr = [4, 5, 2]
```
- **Output:**
```text
[2, 5, 4]Explanation: The elements of the array are [4, 5, 2]. The reversed array will be [2, 5, 4].
```

##### Example 3

- **Input:**
```text
arr = [1]
```
- **Output:**
```text
[1]Explanation: The array has only single element, hence the reversed array is same as the original.
```

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (C++)

- **Submitted:** 2026-10-20 18:11:17
- **Status:** Correct
- **Marks:** 2

```cpp
class Solution {
  public:
    void reverseArray(vector<int> &arr) {
        // code here
        int n= arr.size();
        vector<int> temp(n);
        
        for (int i=0; i<n;i++){
        temp[i]=arr[n-i-1];
        }
        for (int i = 0; i < n; i++){
        arr[i] = temp[i];
        }
    }
};

/*if n=4
i=0; 0<4--temp[0]=arr[3]
i=1; 1<4--temp[1]=arr[2]
i=2; 2<4--temp[2]=arr[1]
i=3; 3<4--temp[3]=arr[0]
i=4; 4<4 false-out of loop
print reverse*/
```

*Generated on: 10/20/2026, 6:11:47 PM*