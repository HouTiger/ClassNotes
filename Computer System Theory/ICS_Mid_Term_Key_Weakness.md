# ICS 期中复习知识点整理
[TOC]
## Floating point
* Numerical Form: ${(-1)} ^ s M 2 ^ E$

|   | s | exp | frac|  
|---|---|---|---|
| 32 bits | 1 bits | 8 bits | 23 bits |  
| 64 bits | 1 | 11 | 52 |  

### Normalized
* exp $\ne$ 000...0 and exp $\ne$ 111...1
* form: ${(-1)} ^ s * 1.frac * 2 ^ E$  
* E = exp - bias
    * if exp = k bits long  
        bias = $2 ^ {k - 1} - 1$  
    * notice:  
        $exp_{max} =$ 0xFFF...F0, which equals $2 ^ k - 2 $
### Denormalized  
* exp = 000...0  
* form: ${(-1)} ^ s * 0.frac * 2 ^ {1 - bias}$  
### special number
* exp = 111...1
* $\infty$
    * frac = 000...0
    * example: 1.0/0.0 = −1.0/−0.0 = +$\infty$, 1.0/−0.0 = −$\infty$
* NaN
    * frac $\ne$ 000...0
    * example: $\sqrt{-1}, \infty - \infty, \infty * 0$

## x86-64 ISA
* Condition Codes **(CC)**
    * CF: unsigned overflow
        `(unsigned) t < (unsigned) a `
        
    * ZF:  
        `t == 0 `
    * SF:
        `t < 0`  
    * OF: signed overflow
        `(a < 0 == b < 0) && (t < 0 != a < 0)`
* 
### Instructions that set CC


### Instructions that don't set CC




