__Presentations__: Four lectures -> Exams -> Presentations
Chapter 31 - he's not positive
Homework Review:
I'm taking images of solutions. If you need any, let me know and I'll send them over. 

# Discussion leading up to RSA 
RSA is a scheme for cryptology. We don't know if its secure supposedly...

Let m, n $\epsilon$ $Z^+$ 
definitions: 
	We say m divides n (m/n) iff mod m
	n > 1 is prime iff m/n -> m=1 or m = n, otherwise it is composite

**Unique factorization theorem**: Every integer n > 1 can be uniquely written as n = .... if you multiply numbers, and the values are all primes, it cant be factored down. if it features composite numbers, it can. Ex: 3 * 3 cannot be broken down, but 3 * 6 can become 3 * 3 * 2.

theorem: There are infinitely many primes -> easy to disprove by contradiction

Prime # Theorem: Letting $\pi(x)$ denote the # of of primes $\epsilon[2, x], lim_{x->\infty}(\pi(x)lnx)/x$ 
In short. as x grows, the total number of primes grow like x/lnx

There are a a lot of primes I reckon... 

Observation: Letting d(n) denote the 

I have no idea what he's saying. 

https://mathworld.wolfram.com/PrimeNumberTheorem.html

d(n) = (1 +a_1)(1+a_2)...(a+a_e)

gcd(m, n) is the largest integer that can divide into m and n. 

$\phi(n)$ (the euler totient function) is used to denote the # of integers [1, n] that are relatively prime to n. for example, [1,6] is 1 and 5. 

$\phi(n)$ = n(1 - 1/p_1)(1-1/p_2)...(1-1/p_d)

eg

$\phi(6 = 2 * 3)$ = 6(1-1/2)(1-1/3) = 6(1/2)(2/3) = 2 = |{1, 5}| ?

Euclidean alg for gcd: 

fcn gcd(n, m) {
if m = 0 then gcd <- n
else gcd = gcd(m, n mod m)
}

Primarily Testing: Polynomial time -> need O((log n)^c)
Sieve method: O(sqrt(n)), too slow

Fermots little theorem: if n is prime, then for all b not divisible by n, we have b^n-1 === 1. What?

Group Axons: Inverse, closure, associative, identity