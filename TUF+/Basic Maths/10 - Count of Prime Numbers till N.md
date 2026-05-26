
Easy

You are given an integer n. You need to find out the number of prime numbers in the range `[1, n]` (inclusive). Return the number of prime numbers in the range.

A prime number is a number which has no divisors except, 1 and itself.

	Example 1
	
	Input: n = 6
	
	Output: 3
	
	Explanation: Prime numbers in the range [1, 6] are 2, 3, 5.
	
	Example 2
	
	Input: n = 10
	
	Output: 4
	
	Explanation: Prime numbers in the range [1, 10] are 2, 3, 5, 7.
	
	Constraints
	
	2 <= n <= 1000


---

## Solution - Brute

```cpp
private:

    bool isPrime(int n) {
		
        int count = 0;
			
        for (int i = 1; i <= n; i++) {
				
            if (n % i == 0) {
	            
                count++;
	            
            }
			
        }
			
        return count == 2;
    }

public:
	
    int primeUptoN(int n) {
		
        int count = 0;
			
        for (int i = 1; i <= n; i++) {
			
            if (isPrime(i)) count++;
        }
			
        return count;
		
    }
```


### Complexity:

**Time Complexity** : O(n^2)

**Space Complexity** : O(1)

---

# Solution - Optimal

	- Loop til sqrt(n)


```cpp
   private:
       bool isPrime(int n) {
           int count = 0;
		
           for (int i = 1; i <= sqrt(n); ++i) {
               if (n % i == 0) {
                   count++;
				
                   if (n % i != i) {
                       count++;
                   }
               }
           }
			
           if (count == 2) return true;
           return false;
       }
		
   public:
       int primeUptoN(int n) {
           int count = 0;
		
           for (int i = 2; i <= n; i++) {
               if (isPrime(i)) count++;
           }
		
           return count;
       }
```


### Complexity:

**Time Complexity** : O(n^3/2)

**Space Complexity** : O(1)

---
