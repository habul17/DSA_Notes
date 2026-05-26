
Easy

You are given two integers n1 and n2. You need find the Greatest Common Divisor (GCD) of the two given numbers. Return the GCD of the two numbers.

The Greatest Common Divisor (GCD) of two integers is the largest positive integer that divides both of the integers.

	Example 1
	
	Input: n1 = 4, n2 = 6
	
	Output: 2
	
	Explanation: Divisors of n1 = 1, 2, 4, Divisors of n2 = 1, 2, 3, 6
	
	Greatest Common divisor = 2.
	
	Example 2
	
	Input: n1 = 9, n2 = 8
	
	Output: 1
	
	Explanation: Divisors of n1 = 1, 3, 9 Divisors of n2 = 1, 2, 4, 8.
	
	Greatest Common divisor = 1.
	
	Constraints
	
	1 <= n1, n2 <= 1000

---

# Solution - Brute

	- Loop till minimum of n1 and n2 and return the greatest divisor 
	which divides both. 


```cpp
int GCD(int n1, int n2) {
	
    int divisor = 0;
		
    for (int i = 1; i <= min(n1, n2); i++) {
        if (n1 % i == 0 && n2 % i == 0) {
            divisor = i;
        }
    }
		
    return divisor;
	
}
```


### Complexity:

**Time Complexity** : O(min(n1, n2)) 

**Space Complexity** : O(1)

---

# Solution - Better

	- Loop reverse and return the first divisor which divides both.


```cpp
 int GCD(int n1, int n2) {
	
     for (int i = min(n1, n2); i >= 0; i--) {
         if (n1 % i == 0 && n2 % i == 0) {
             return i;
         }
     }
	
 }
```


### Complexity:

**Time Complexity** : O(min(n1, n2)) 

**Space Complexity** : O(1)

---


# Solution - Optimal


	- Use Euclidean Algorithm

```cpp
int GCD(int n1, int n2) {
	
    while (n1 > 0 && n2 > 0) {
		
        if (n1 > n2) {
            n1 = n1 % n2;
        } else {
            n2 = n2 % n1;
        }
    }
		
    if (n1 == 0) return n2;
	
    return n1;
	
}
```

### Complexity:

**Time Complexity** : O(log(min(n1, n2))) 

**Space Complexity** : O(1)

---
