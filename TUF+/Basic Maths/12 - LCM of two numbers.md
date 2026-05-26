
Easy

You are given two integers n1 and n2. You need find the Lowest Common Multiple (LCM) of the two given numbers. Return the LCM of the two numbers.

The Lowest Common Multiple (LCM) of two integers is the lowest positive integer that is divisible by both the integers.

	Example 1
	
	Input: n1 = 4, n2 = 6
	
	Output: 12
	
	Explanation: 4 * 3 = 12, 6 * 2 = 12.
	
	12 is the lowest integer that is divisible both 4 and 6.
	
	Example 2
	
	Input: n1 = 3, n2 = 5
	
	Output: 15
	
	Explanation: 3 * 5 = 15, 5 * 3 = 15.
	
	15 is the lowest integer that is divisible both 3 and 5.
	
	Constraints
	
	1 <= n1, n2 <= 1000

---

# Solution - Brute

	- Find max , Find multiple of max , Return the first number which 
	is divisible by both n1 & n2


```cpp
int LCM(int n1, int n2) {
	
    int lcm;
	
    int n = max(n1, n2);
    int i = 1;
	
    while (1) {
        int mul = n * i;
		
        if (mul % n1 == 0 && mul % n2 == 0) {
            lcm = mul;
            break;
        }
        i++;
    }
    return lcm;
}
```

### Complexity:

**Time Complexity** : O(min(n1, n2)) 

**Space Complexity** : O(1)

---

# Solution - Optimal

	- Use Formula : n1 * n2 / gcd(n1, n2)


```cpp
private:
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

public:
    int LCM(int n1, int n2) {
        int gcd = GCD(n1, n2);
		
        int lcm = (n1 * n2) / gcd;
		
        return lcm;
    }
```

### Complexity:

**Time Complexity** : O(log(min(n1, n2))) 

**Space Complexity** : O(1)

---
