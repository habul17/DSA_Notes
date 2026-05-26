
Easy

You are given an integer **n**. You need to check if the number is a **perfect** number or not. Return **true** if it is a **perfect** number, otherwise, return **false**.

A **perfect** number is a number whose proper **divisors** (excluding the number itself) add up to the number **itself**.

	Example 1
	
	Input: n = 6
	
	Output: true
	
	Explanation: Proper divisors of 6 are 1, 2, 3.
	
	1 + 2 + 3 = 6.
	
	Example 2
	
	Input: n = 4
	
	Output: false
	
	Explanation: Proper divisors of 4 are 1, 2.
	
	1 + 2 = 3.
	
	Constraints
	
	- 1 <= n <= 5000


--- 

## Solution - Brute


```cpp
bool isPerfect(int n) {
	
    int original = n;
    int sum = 0;
	
    for (int i = 1; i < n - 1; i++) {
        if (n % i == 0) {
            sum += i;
        }
    }
		
    return sum == original;
}
```


### Complexity:

**Time Complexity** : O(n) 

**Space Complexity** : O(1)

---

## Solution - Optimal

	- Loop till sqrt(n) or i * i < n (better)


```cpp
bool isPerfect(int n) {
	
    if (n == 1) return false;
	
    int sum = 0;
	
    for (int i = 1; i <= sqrt(n); ++i) {
		
        if (n % i == 0) {
            sum += i;
            
            if (i != n / i && n / i != n) {
                sum += n / i;
            }
        }
		
    }
		
    return n == sum;
		
}
```


### Complexity:

**Time Complexity** : O(sqrt(n)) 

**Space Complexity** : O(1)

---