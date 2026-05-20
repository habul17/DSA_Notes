
Easy

You are given an integer **n**. Return the integer formed by placing the **digits** of n in **reverse** order.

	Example 1
	
	Input: n = 25
	
	Output: 52
	
	Explanation: Reverse of 25 is 52.
	
	Example 2
	
	Input: n = 123
	
	Output: 321
	
	Explanation: Reverse of 123 is 321.
	
	Example 3
	
	Input: n = 54
	
	Output:
	
	45
	
	Constraints
	
	- 0 <= n <= 5000
	- n will contain no leading zeroes except when it is 0 itself.

---

## Solution:

	- Extract the last digit and do (num * 10) + last digit.


```cpp
int reverseNumber(int n) {
	
    int num = 0;
	
    while (n > 0) {
		
        int lastDigit = n % 10;
		
        num = (num * 10) + lastDigit;
		
        n /= 10;
    }
		
    return num;
		
}
```


### Complexity:

**Time Complexity** : O(log10(n)) 

**Space Complexity** : O(1)

---

