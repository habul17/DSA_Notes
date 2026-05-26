
Easy

You are given an integer **n**. You need to check whether it is an **armstrong** number or not. Return **true** if it is an **armstrong** number, otherwise return **false**.

An **armstrong** number is a number which is **equal** to the **sum** of the **digits** of the number, raised to the **power** of the **number** of digits.

	Example 1
	
	Input: n = 153
	
	Output: true
	
	Explanation: Number of digits : 3.
	
	13 + 53 + 33 = 1 + 125 + 27 = 153.
	
	Therefore, it is an Armstrong number.
	
	Example 2
	
	Input: n = 12
	
	Output: false
	
	Explanation: Number of digits : 2.
	
	12 + 22 = 1 + 4 = 5.
	
	Therefore, it is not an Armstrong number.
	
	Example 3
	
	Input: n = 370
	
	Output:
	
	true
	
	Constraints
	
	- 0 <= n <= 109


---

## Solution


```cpp
bool isArmstrong(int n) {

    int copy = n;
    int count = log10(n) + 1;
    int ans = 0;
	
    while (n > 0) {
		
        int lastDigit = n % 10;
		
        ans += pow(lastDigit, count);
		
        n /= 10;
    }
	
    return copy == ans;
	
}
```


### Complexity:

**Time Complexity** : O(log10(n)) 

**Space Complexity** : O(1)

---

