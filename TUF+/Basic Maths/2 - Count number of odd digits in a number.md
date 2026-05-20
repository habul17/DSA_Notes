
Easy

You are given an integer **n**. You need to **return** the **number** of **odd** digits present in the number.

The number will have **no** leading zeroes, except when the number is **0** itself.

	Example 1
	
	Input: n = 5
	
	Output: 1
	
	Explanation: 5 is an odd digit.
	
	Example 2
	
	Input: n = 25
	
	Output: 1
	
	Explanation: The only odd digit in 25 is 5.
	
	Example 3
	
	Input: n = 15
	
	Output:
	
	2
	
	Constraints
	
	- 0 <= n <= 5000
	- n will contain no leading zeroes except when it is 0 itself.

---

## Solution:

	- Extract Digits by n % 10 & increase the count if digit is odd.


```cpp
int countOddDigit(int n) {
    
    int countOdd = 0;
	
    while (n > 0) {
		
        if (n % 2 == 1) {
		
            countOdd++;
			
        }
		
        n = n / 10;
    }
    return countOdd;
}
```


### Complexity:

**Time Complexity** : O(log10(n)) 

**Space Complexity** : O(1)

---

