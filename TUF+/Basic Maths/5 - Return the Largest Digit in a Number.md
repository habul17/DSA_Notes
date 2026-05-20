
Easy

You are given an integer **n**. Return the **largest digit** present in the number.

	Example 1
	
	Input: n = 25
	
	Output: 5
	
	Explanation: The largest digit in 25 is 5.
	
	Example 2
	
	Input: n = 99
	
	Output: 9
	
	Explanation: The largest digit in 99 is 9.
	
	Example 3
	
	Input: n = 1
	
	Output:
	
	1
	
	Constraints
	
	- 0 <= n <= 5000
	- n will contain no leading zeroes except when it is 0 itself.

---

## Solution:

	- Extract the last digit and check if it is the largest.


```cpp
int largestDigit(int n) {
	
    int largest = 0;
	
    while (n > 0) {
		
        int lastDigit = n % 10;
		
        if (lastDigit > largest) {
            largest = lastDigit;
        }
			
        n /= 10;
    }
		
    return largest;
		
}
```


### Complexity:

**Time Complexity** : O(log10(n)) 

**Space Complexity** : O(1)

---

