# Homework1
#### 侯太格 1600012897
## 1. 
* Let {$p_n$} be the sequence defined by $p_n = \sum_{k = 1}^n {\frac{1}{k}}$. Show that {$p_n$} diverges even though $\lim_{n\to\infty}{(p_n - p_{n - 1}) = 0}$ 
* **Proof**
	$p_{2 ^ k} = \sum_{t = 1} ^ {2^k} \frac {1}{t}= 1 + \sum_{n = 1} ^ k \sum_{i = 2 ^ {n - 1} + 1} ^ {2 ^ n} \frac {1}{i} \; > 1 + \sum_{n = 1} ^ k \sum_{i = 2 ^ {n - 1} + 1} ^ {2 ^ n} \frac {1}{2 ^ n} = 1 + \sum_{n = 1} ^ {k} \frac {1} {2} = 1 + \frac {k} {2}$  
	for any $P_n$, there is a $p_{n - 1} < 2 ^ k < p_n$, 
	so $p_n > 1 + \frac {\log {(n - 1)}} {2}$, it diverges.

## 2.
* The fuction defined by $f(x) = sin(\pi x)$ has zeros at every integer. Show that when $-1 < a < 0$ and $2 < b < 3$，the Bisection method converges to
* a. $0$. if $a + b < 2$
	$f(a) < 0, f(b) > 0$  
	Because $\frac{1}{2} < \frac {a + b}{2} < 1$, so $f(\frac {a + b}{2}) > 0$, the root between $(a, \frac{a + b}{2})$ is 0.


*	b. $2$. if $a + b > 2$
	$1 < \frac{a + b}{2} < \frac {3}{2}$, so $f(\frac {a + b}{2}) < 0$, the root between $(\frac{a + b}{2}, b)$ is 2.
*	c. $1$. if $a + b = 2$ 
	if $a + b = 2$, then $s = \frac {a + b}{2} = 1$, $f(s) = f(1) = sin \pi  = 0$



## 3. 
* Let $W(x)$ be the Wilkinson polynomial. 
    * (a) Prove that $W^\prime(16) = 15!4!$
		$W(x) = (x - 16)g(x)$
		$W^\prime(x) = g(x) + (x - 16)g^\prime(x)$
		$W^\prime(16) = g(16) = (16 - 1)...(16 - 15)(16 - 17)...(16 - 20) = 15!4!$


    * (b) Find an analogous formula for $W^\prime(j)$, where j is an integer between 1 and 20
		$W^\prime(j) = (j - 1)!(-1)^{20 - j}(20 - j)!$

## 4. 
* Suppose that $g$ is continuously differentiable on some interval $(c, d)$ that contains the fixed point $p$ of $g$. Show that if $|g^\prime(p)| < 1$, then there exists a $\delta > 0$ such that if $|p_0 - p| \le \delta$, then the fixed-point iteration converge
* **Proof**
	Let $S = |g ^ {\prime}(p)|$. 
	Because $g$ is continuously differentiable on $(c, d)$, so $g ^ {\prime}$ is continuous on $(c, d)$.  
	And there is a $\delta > 0$, $|g ^ {\prime}| < \frac{S + 1}{2}$ within interval $(p - \delta, p + \delta)$.
	Let $p_i$ denote the iteration in step $i$, then there exits $c_i$ between $p_i$ and $p$, such that $p_{i + 1} - p = g ^ {\prime}(c_i)(p_i - p)$
	If we pick $p_0$ within $(p - \delta, p + \delta)$, then $\frac{|p_{i + 1} - p|}{|p_i - p|} = |g ^ {\prime}(c_i)| < \frac {S + 1}{2} < 1$
	So $\lim_{i \to \infty} p_i = p$,  


## 5.
* If the secant Method converges to r, $f^\prime(r) \ne 0$, then the approximate error relationship $e_{i + 1} \approx |\frac {f^{\prime\prime}(r)}{2f^{\prime}(r)}|e_ie_{i - 1}$ can be shown to hold. Prove that if in addition $\lim_{i\to\infty}\frac{e_{i + 1}} {e_i^{\alpha}}$ exits and is nonzero for some $\alpha > 0$, then $\alpha = \frac {1 + \sqrt{5}}{2}$ and $e_{i + 1} \approx |\frac {f^{\prime\prime}(r)}{2f^{\prime}(r)}| ^ {\alpha - 1}e_i ^ {\alpha}$


## 6.
* Suppose that ${\{p_n\}}$ is superlinearly convergent to p. Show that $\lim_{n\to \infty}\frac {|p_{n + 1} - p_n|}{|p_n - p|} = 1$