## 01. Generating All Subarrays

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/generating-all-subarrays/1)

### Problem Description

**Task:** Given an array arr[], generate and return all possible subarrays. The subarrays must be returned in the following order: 1. Subarrays starting from the first element, followed by subarrays starting from the second element, and so on. 2. For each starting index, subarrays should be in increasing length.

#### Examples

##### Example 1

- **Input:**
```text
arr[] = [1, 2, 3]Output: [[1], [1, 2], [1, 2, 3], [2], [2, 3], [3]]Explanation: Starting with the first element, we generate subarrays [1], [1, 2], and [1, 2, 3]. Then, starting from the second element, we get [2] and [2, 3]. Finally, starting from the third element, we only get [3].
```

##### Example 2

- **Input:**
```text
arr[] = [1, 2]Output: [[1], [1, 2], [2]]Explanation: Starting with the first element, we generate subarrays [1] and [1, 2]. Then, starting from the second element, we get [2].
```

##### Example 3

- **Input:**
```text
arr[] = [1, 1]Output: [[1], [1, 1], [1]]Explanation: Starting with the first element, we generate subarrays [1] and [1, 1] (including both elements). Starting from the second element, we only get the subarray [1].
```

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n^3)
- **Expected Auxiliary Space Complexity:** O(n^3)

### Accepted Solutions (1)

#### Solution 1 (C++)

- **Submitted:** 2026-10-23 16:31:53
- **Status:** Correct
- **Marks:** 2

```cpp
class Solution {
  public:
    vector<vector<int>> getSubArrays(vector<int>& arr) {
        // code here
        vector<vector<int>> ans;
            int n = arr.size();

            for (int i = 0; i < n; i++) {
                for (int j = i; j < n; j++) {
                    vector<int> subarray;

                    for (int k = i; k <= j; k++)
                        subarray.push_back(arr[k]);

                    ans.push_back(subarray);
                }
            }

            return ans;
        }
};

/*if {1,2,3} n=3
i=0,0<3 ; 
j=0,0<3      j=1,1<3      j=2, 2<3
k=0, 0<=0    k=0, 0<=1    k=0, 0<=2
[1]          [1,2]        [1,2,3]

i=1,1<3 ;    
j=1,1<3      j=2,2<3
k=1, 1<=1    k=1, 1<=2
[2]          [2,3]

i=2,2<3 ;
j=2,2<3   
j=2,2<=2
[3]

[[1],[1,2],[1,2,3],[2],[2,3],[3]]*/
```

*Generated on: 10/23/2026, 4:32:36 PM*