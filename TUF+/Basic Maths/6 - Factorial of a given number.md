
Easy

You are given an integer **n**. Return the value of **n!** or **n factorial**.

**Factorial** of a number is the **product** of **all** positive integers less than or equal to that number.

	Example 1
	
	Input: n = 2
	
	Output: 2
	
	Explanation: 2! = 1 * 2 = 2.
	
	Example 2
	
	Input: n = 0
	
	Output: 1
	
	Explanation: 0! is defined as 1.
	
	Example 3
	
	Input: 3
	
	Output:
	
	6
	
	Constraints
	
	- 0 <= n <= 10

---

# Solution

	- Run a for loop from 1 to n and multiply each.


```cpp
int factorial(int n) {
	
    if (n == 0) return 1;
	
    int ans = 1;
	
    for (int i = 1; i <= n; i++) {
		
        ans *= i;
    }
		
    return ans;
		
}
```


### Complexity:

**Time Complexity** : O(n) 

**Space Complexity** : O(1)

---

