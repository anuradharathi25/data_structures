## 01. Stock Buy and Sell – Multiple Transaction Allowed

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/stock-buy-and-sell2615/1)

### Problem Description

**Task:** Given an integer array prices[], where prices[i] is the price of a given stock on the ith day. Each day you may decide to either buy or sell the stock at price[i], you can even buy and sell the stock on the same day, return the maximum profit that you can get.Note: A stock can only be sold if it has been bought previously and multiple stocks cannot be held on any given day.Examples:Input: prices[] = [100, 180, 260, 310, 40, 535, 695]Output: 865Explanation: Buy the stock on day 0 and sell it on day 3 = > 310 – 100 = 210. Buy the stock on day 4 and sell it on day 6 = > 695 – 40 = 655. Maximum Profit = 210 + 655 = 865.Input: prices[] = [4, 2, 2, 2, 4]Output: 2Explanation: Buy the stock on day 3 and sell it on day 4 = > 4 – 2 = 2. Maximum Profit = 2.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (C++)

- **Submitted:** 2026-10-24 00:52:16
- **Status:** Correct
- **Marks:** 4

```cpp
class Solution {
  public:
    int maxProfit(vector<int> &prices) {
        // code here
        int n=prices.size();
        int lMin = prices[0]; 
        int lMax = prices[0];  
        int res = 0;

            int i = 0;
            while (i < n - 1) {
                // Find local minima 
                while (i < n - 1 && prices[i] >= prices[i + 1]) { i++; }
                lMin = prices[i];

                // Local Maxima
                while (i < n - 1 && prices[i] <= prices[i + 1]) { i++; }
                lMax = prices[i];

                // Add current profit 
                res = res + (lMax - lMin);
            }

            return res;
    }
};

/*let n-7
[100, 180, 260, 310, 40, 535, 695]
while(0<6)
while(100>=180) false--lMin=100 out of loop

while(100<=180) true i++ i=1
while(180<=260) true i++ 1=2
while(260<=310) true i++ 1=3
while(310<=40) false lMax=310

res=0+(310-100)
return 210

now i=3
while(3<6)
while(310>=40) true i++ i=4
while(40>=535) false lMin-40

while(40<=535) true i++ i=5
while(535<=695) true i++ i=6 lMax=695

res=210+(695-40)
return 865 */
```

*Generated on: 10/24/2026, 12:52:47 AM*