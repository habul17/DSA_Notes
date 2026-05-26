
Easy

You are given an integer n. You need to find all the divisors of n. Return all the divisors of n as an array or list in a sorted order.

A number which completely divides another number is called it's divisor.

	Example 1
	
	Input: n = 6
	
	Output = [1, 2, 3, 6]
	
	Explanation: The divisors of 6 are 1, 2, 3, 6.
	
	Example 2
	
	Input: n = 8
	
	Output: [1, 2, 4, 8]
	
	Explanation: The divisors of 8 are 1, 2, 4, 8.
	
	Example 3
	
	Input: n = 7
	
	Output:
	
	[1, 7]
	
	Constraints
	
	1 <= n <= 1000

---

# Solution - Brute

	- Loop 1 -> n and Find the divisors & add it to the vector.


```cpp
vector < int > divisors(int n) {
	
    vector < int > ans;
		
    for (int i = 1; i <= n; i++) {
        if (n % i == 0) {
            ans.push_back(i);
        }
    }
	
    return ans;
	
}
```

### Complexity:

**Time Complexity** : O(n) 

**Space Complexity** : O(k)

	- k is the number of divisors

---

# Solution - Optimal I


	- Loop from 1 -> sqrt(n)


```cpp
vector < int > divisors(int n) {
	
    vector < int > ans;
	
    for (int i = 1; i * i <= n; i++) {
		
        if (n % i == 0) {
			
            ans.push_back(i);
			
            if (i != n / i) {
                ans.push_back(n / i);
            }
			
        }
    }
		
    sort(ans.begin(), ans.end());
	
    return ans;
	
}
```


### Complexity:

**Time Complexity** : O(sqrt(n) + (k * log(k))

	- k * log(k) for sorting the array

**Space Complexity** : O(k)

	- k is the number of divisors

---


# Solution - Optimal II

	- Avoid sorting step by using 2 vectors , one stores the smallest 
	divisors and another one stores its subsequent largest divisor in 
	reverse order.


```cpp
vector < int > divisors(int n) {
	
    vector < int > smallDivisor;
    vector < int > largeDivisor;
	
    for (int i = 1; i * i <= n; i++) {
		
        if (n % i == 0) {
            smallDivisor.push_back(i);
			
            if (i != n / i) {
                largeDivisor.push_back(n / i);
            }
			
        }
    }
		
    for (int i = largeDivisor.size() - 1; i >= 0; i--) {
        smallDivisor.push_back(largeDivisor[i]);
    }
		
    return smallDivisor;
}
```

### Complexity:

**Time Complexity** : O(sqrt(n))

**Space Complexity** : O(k)

	- k is the number of divisors

---
