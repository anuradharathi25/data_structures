## 01. Stock Buy and Sell – Max one Transaction Allowed

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/buy-stock-2/1)

### Problem Description

**Task:** Given an array prices[] of non-negative integers, representing the prices of the stocks on different days. The task is to find the maximum profit possible by buying and selling the stocks on different days when at most one transaction is allowed. Here one transaction means 1 buy + 1 Sell. If it is not possible to make a profit then return 0.

> **Note:** Stock must be bought before being sold.

#### Examples

##### Example 1

- **Input:**
```text
prices[] = [7, 10, 1, 3, 6, 9, 2]Output: 8Explanation: You can buy the stock on day 2 at price = 1 and sell it on day 5 at price = 9. Hence, the profit is 8.
```

##### Example 2

- **Input:**
```text
prices[] = [7, 6, 4, 3, 1]Output: 0 Explanation: Here the prices are in decreasing order, hence if we buy any day then we cannot sell it at a greater price. Hence, the answer is 0.
```

##### Example 3

- **Input:**
```text
prices[] = [1, 3, 6, 9, 11]Output: 10 Explanation: Since the array is sorted in increasing order, we can make maximum profit by buying at price[0] and selling at price[n-1].
```

#### Constraints

- **1.** `1 ≤ prices.size() ≤ 10⁵⁰ ≤ prices[i] ≤ 10⁴`

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (C++)

- **Submitted:** 2026-10-23 22:22:15
- **Status:** Correct
- **Marks:** 2

```cpp
class Solution {
  public:
    int maxProfit(vector<int> &prices) {
        // code here
        int minSoFar = prices[0], res = 0;
            for (int i = 1; i < prices.size(); i++) {
                minSoFar = min(minSoFar, prices[i]);

                res = max(res, prices[i] - minSoFar);
            }
            return res;
    }
};       

// prices.size()=6
// i=1,1<6--minSoFar= min(7,1);res=max(0,-6)
// i=2,2<6--minSoFar= min(1,5);res=max(0,4)
// i=3,3<6--minSoFar= min(1,3);res=max(4,2)
// i=4,4<6--minSoFar= min(1,6);res=max(4,5)
// i=5,5<6--minSoFar= min(1,4);res=max(5,3)
// return 5


/*{7,1,5,3,6,4}
n=6
i=0,0<5
j=1,1<6--profit= max(0,-6)
j=2,2<6--profit= max(0,-2)
j=3,3<6--profit= max(0,-4)
j=4,4<6--profit= max(0,-1)
j=5,5<6--profit= max(0,-3)

i=1,1<5
j=2,2<6--profit= max(0,4)
j=3,3<6--profit= max(4,2)
j=4,4<6--profit= max(4,5)
j=5,5<6--profit= max(5,3)  profit=5

i=2,2<5
j=3,3<6--profit= max(5,-2)
j=4,4<6--profit= max(5,1)
j=5,5<6--profit= max(5,-1)

i=3,3<5
j=4,4<6--profit= max(5,3)
j=5,5<6--profit= max(5,1)

i=4,4<5
j=5,5<6--profit= max(5,-2) 
return profit=5
*/
```

*Generated on: 10/23/2026, 10:24:24 PM*