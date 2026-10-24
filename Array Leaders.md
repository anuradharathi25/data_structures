## 01. Array Leaders

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/leaders-in-an-array-1587115620/1)

### Problem Description

**Task:** You are given an array arr of positive integers. Your task is to find all the leaders in the array. An element is considered a leader if it is greater than or equal to all elements to its right. The rightmost element is always a leader.Examples:Input: arr = [16, 17, 4, 3, 5, 2]

#### Examples

##### Example 1

- **Output:**
```text
[17, 5, 2]
```
- **Explanation:** Note that there is nothing greater on the right side of 17, 5 and, 2.

##### Example 2

- **Input:**
```text
arr = [10, 4, 2, 4, 1]
```
- **Output:**
```text
[10, 4, 4, 1]Explanation: Note that both of the 4s are in output, as to be a leader an equal element is also allowed on the right. sideInput: arr = [5, 10, 20, 40]Output: [40]Explanation: When an array is sorted in increasing order, only the rightmost element is leader.Input: arr = [30, 10, 10, 5]Output: [30, 10, 10, 5]Explanation: When an array is sorted in non-increasing order, all elements are leaders.
```

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (C++)

- **Submitted:** 2026-10-24 20:58:35
- **Status:** Correct
- **Marks:** 2

```cpp
class Solution {
  public:
    vector<int> leaders(vector<int>& arr) {
        // code here
        vector<int> res; 
            int n = arr.size();
            int maxRight = arr[n - 1]; 
            res.push_back(maxRight); 

            for (int i = n - 2; i >= 0; i--) {

                if (arr[i] >= maxRight) {
                    maxRight = arr[i]; 
                    res.push_back(maxRight); 
                }
            }
            reverse(res.begin(), res.end());

        return res; 

    }
};

/*n=6 [16, 17, 4, 3, 5, 2]
maxRight=arr[5]=2
i=4,4>=0
if(5>=2)--maxRight=5 ..res=[2,5]
i=3,3>=0
if(3>=5)--false
1=2,2>=0
if(4>=5)--false
i=1,1>=0
if(17>=5)--maxRight=17 ..res=[2,5,17]
i=0,0>=0
if(16>=17)--false

reverse res [17,5,2]


*/
```

*Generated on: 10/24/2026, 9:00:37 PM*