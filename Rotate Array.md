## 01. Rotate Array

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/rotate-array-by-n-elements-1587115621/1)

### Problem Description

**Task:** Given an array arr[]. Rotate the array to the left (counter-clockwise direction) by d steps, where d is a positive integer. Do the mentioned change in the array in place.Note: Consider the array as circular.Examples :Input: arr[] = [1, 2, 3, 4, 5], d = 2

#### Examples

##### Example 1

- **Output:**
```text
[3, 9, 1, 7]
```
- **Explanation:** when we rotate 9 times, we'll get [3, 9, 1, 7] as resultant array.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (C++)

- **Submitted:** 2026-10-22 00:25:00
- **Status:** Correct
- **Marks:** 1

```cpp
class Solution {
  public:
    void rotateArr(vector<int>& arr, int d) {
        // code here
        int n=arr.size();
        d=d%n;
        reverse(arr.begin(), arr.begin()+d);
        
        reverse(arr.begin() + d, arr.end());
        
        reverse(arr.begin(), arr.end());
        
    }
};

/*let n=5;d=2
i=0; 0<2--
first=arr[0]
j=0; 0<4
arr[0]=arr[1]
j=1; 1<4
arr[1]=arr[2]
j=2; 2<4
arr[2]=arr[3]
j=3; 3<4
arr[3]=arr[4]
j=0 condition false out of j loop

i=1; 1<2--
first=arr[4]
j=0; 0<4
arr[0]=arr[1]
j=1; 1<4
arr[1]=arr[2]
j=2; 2<4
arr[2]=arr[3]
j=3; 3<4
arr[3]=arr[4]
j=0 condition false out of j loop

i=2; 2<2 false ---out of i loop
*/
```

*Generated on: 10/22/2026, 12:25:47 AM*