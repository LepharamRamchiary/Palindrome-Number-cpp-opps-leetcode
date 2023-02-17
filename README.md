**# Palindrome Number in C++(oops)**

**Question**

Given an integer x, return true if x is a palindrome, and false otherwise.

Example 1:
```
Input: x = 121
Output: true
Explanation: 121 reads as 121 from left to right and from right to left.
```
Example 2:
```
Input: x = -121
Output: false
Explanation: From left to right, it reads -121. From right to left, it becomes 121-. Therefore it is not a palindrome.
```
Example 3:
```
Input: x = 10
Output: false
Explanation: Reads 01 from right to left. Therefore it is not a palindrome.
```

**Solution**:-
```c++
#include<bits/stdc++.h>

using namespace std;

class Solution {
public:
    bool isPalindrome(int x) {
        stack<int> st;
        if (x < 0) {
            return false;
        }
        int y = x;
        while (x) {
            st.push(x % 10);
            x /= 10;
        }
        while (y) {
            if (st.top() != (y % 10)) {
                return false;
            }
            st.pop();
            y /= 10;
        }
        return true;
    }
};

int main() {
    int x;
    cout << "Enter a number: ";
    cin >> x;

    Solution sol;
    if (sol.isPalindrome(x)) {
        cout << x << " is a palindrome." << endl;
    } else {
        cout << x << " is not a palindrome." << endl;
    }

    return 0;
}
