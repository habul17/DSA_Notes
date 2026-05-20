
Easy

You are given an integer **n**. You need to **return** the **number** of digits in the number.

The number will have **no** leading zeroes, except when the number is **0** itself.

	Example 1
	
	Input: n = 4
	
	Output: 1
	
	Explanation: There is only 1 digit in 4.
	
	Example 2
	
	Input: n = 14
	
	Output: 2
	
	Explanation: There are 2 digits in 14.
	
	Constraints
	
	- 0 <= n <= 5000
	- n will contain no leading zeroes except when it is 0 itself.


---

## Solution - 1

	Dividing the digit by 10.
	

```cpp
int countDigit(int n) {

    if (n == 0) return 1;
    
    int count = 0;
    
    while (n > 0) {
        count++;
        n /= 10;
    }
    
    return count;
}
```


### Complexity:

**Time Complexity** : O(log10(n)) - In every iteration we are dividing n by 10.

**Space Complexity** : O(1)


---


## Solution - 2

	Using direct formula - log10(n) + 1


```cpp
int countDigit(int n) {
	
    if (n == 0) return 1;
	
    int count = log10(n) + 1;
	
    return count;
}
```


### Complexity:

**Time Complexity** : O(1) 

**Space Complexity** : O(1)

---

