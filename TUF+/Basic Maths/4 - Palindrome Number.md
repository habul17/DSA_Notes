
Easy

You are given an integer **n**. You need to check whether the number is a **palindrome** number or not. Return **true** if it's a **palindrome** number, otherwise return **false**.

A **palindrome** number is a number which reads the **same** both **left to right** and **right to left**.

	Example 1
	
	Input: n = 121
	
	Output: true
	
	Explanation: When read from left to right : 121.
	
	When read from right to left : 121.
	
	Example 2
	
	Input: n = 123
	
	Output: false
	
	Explanation: When read from left to right : 123.
	
	When read from right to left : 321.
	
	Constraints
	
	- 0 <= n <= 5000
	- n will contain no leading zeroes except when it is 0 itself.


---

## Solution:

	- Store the original number , reverse the number and check both equal or not.


```cpp
bool isPalindrome(int n) {
	
    int original = n;
	
    int num = 0;
	
    while (n > 0) {
		
        int lastDigit = n % 10;
		
        num = (num * 10) + lastDigit;
		
        n /= 10;
    }
		
    return num == original;
		
}
```


### Complexity:

**Time Complexity** : O(log10(n)) 

**Space Complexity** : O(1)

---

