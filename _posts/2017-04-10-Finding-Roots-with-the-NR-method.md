---
title: "Finding roots with the Newton-Raphson method (I)"
layout: post
mathjax: true
date: 2017-04-10
tag:
- Python
- Math
- Optimization
- MLE
- Tutorial
category: blog
author: Samuel L Hong
description: Finding Roots with the Newton-Raphson method
---


The Newton-Raphson  (NR) method is an iterative method to find the roots of a function. The method assumes that the funciton $f$ we are interested in has a continuous derivative. Our goal is to find $x : f(x)=0$

# NR in one variable

Let $f$ be a continuous function $f:\mathbb{R} \rightarrow \mathbb{R}$, with a continuous derivative $f'$. Given $f$, $f'$ and a starting point $x_0$  from the domain, we can iteratively find the root of the equaton by applying:

$$
x_1 = x_0 - \frac{f(x_0)}{f'(x_0)}
$$

The process is repeated until a sufficiently accurate value $\delta$ is reached:

$$
x_n = x_{n-1} - \frac{f(x_{n-1})}{f'(x_{n-1})} \\
\left|x_n-x_{n-1}\right| \leq \delta
$$

This iterative method for finding successively better approximations to the roots of $f$ is called he Newton–Raphson method (also called Newton's method)

## Implementation

We will now implement NR to find the roots of the function $f(x) = 4x^2 - 7x + 1$. 

Recall the requirements to implement NR:
* A continuous function defined in $\mathbb{R}$
* The derivative of such function 
* A starting point $x_0$
* An accuracy threshold $\delta$

Notice that $f(x)$ is continuous with derivative $f'(x)=8x-7$. Thus, we only have to choose values for $x_0$ and $\delta$ to start with our implementation.

We know from WolframAlpha that the roots to this equation are given by $x = \frac{1}{8} (7 \pm \sqrt{33})$

Let $x_0=\pm10$ and $\delta = 0.001$. Our NR implementation is thus:


```python
import math
ROOT1 = 1/8*(7-math.sqrt(33))
ROOT2 = 1/8*(7+math.sqrt(33))

def f(x):
    return 4*x*x - 7*x +1

def f_prime(x):
    return 8*x-7

def NR(f,x0,delta):
    x_initial = x0
    #initialize x_n+1 so that the while loop holds
    x_next = x0+delta*20
    while abs(x_next-x_initial)>delta:
        x_initial = x_next 
        x_next = x_initial - f(x_initial)/f_prime(x_initial)
    return x_next

NR_ROOT1 = NR(f,-10,0.001)
NR_ROOT2 = NR(f,10,0.001)
```
We can see that this algorithm converges to the roots:

```python
> round(ROOT1,4),round(NR_ROOT1,4)
(0.15693, 0.15693)
> round(ROOT2,6),round(NR_ROOT2,6)
(1.59307, 1.59307)
```
## NR using finite difference approximations

Sometimes, our function can be so complex to the point where calculating the derivative beforehand is too taxing (or tedious). We can approximate the derivative by using the finite difference approximation.

Recall the definition of derivative:

$$
f'(x) = lim_{h\rightarrow \infty} \frac{f(x+h)-f(x)}{h}
$$

The finite difference approximation consists of removing the limit from the expression, and fixing $h$ to an appropriately small value:

$$
f'(x) \approx \frac{f(x+h)-f(x)}{h}
$$

The numerator in this expression is called the *forward difference*. Alternative definitions of the derivative can be used by using the *backwards difference* of the *central difference*:

$$
f'(x) \approx \frac{f(x)-f(x-h)}{h} \\
f'(x) \approx \frac{f(x+\frac{1}{2}h)-f(x-\frac{1}{2}h)}{h}
$$

We can thus, implement NR using the same approach that we previously described, but replacing the derivative for the finite difference approximation. For $f(x) = 4x^2 - 7x + 1$ and using the forward difference approximation, we get:


```python
def f(x):
    return 4*x*x - 7*x +1

def f_prime_FD(f,x,h):
    return (f(x+h)-f(x))/h

def NR_FD(f,x0,delta,h):
    x_initial = x0
    #initialize x_n+1 so that the while loop holds
    x_next = x0+delta*20
    while abs(x_next-x_initial)>delta:
        x_initial = x_next 
        x_next = x_initial - f(x_initial)/f_prime_FD(f,x_initial,h)
    return x_next
    
NR_ROOT1_FD = NR_FD(f,-10,0.001,0.0001)
NR_ROOT2_FD = NR_FD(f,10,0.001,0.0001)
```
We can verify that this approximations yield the same results

```python
> round(ROOT1,6),round(NR_ROOT1,6),round(NR_ROOT1_FD,6)
(0.15693, 0.15693, 0.15693)
> round(ROOT2,4),round(NR_ROOT2,6),round(NR_ROOT2_FD,6)
round(ROOT2,6),round(NR_ROOT2,6),round(NR_ROOT2_FD,6)
(1.59307, 1.59307, 1.59307)
```

# Optimization

We can also use NR to find critical points of continuous real functions. Recall that the critical point of a differentiable real function is any value in its domain where its derivative is 0:

$$
x_{crit} = \{x: f'(x)=0\}
$$

Thus, we can use NR on $f'$ to get the critical points of $f$:

$$
x_{n+1} = x_n - \frac{f'(x_n)}{f''(x_n)}
$$

Recall that our function $f(x)=4x^2 - 7x + 1$ is a quadratic function and thus has a single critical point. We can optimize $f$ by slightly tweaking our code used to find roots with NR:

```python

def f_prime(x):
    return 8*x-7

def f_second_derivative(x)
    return 8
    
def NR_Optimize(x0,delta):
    x_initial = x0
    #initialize x_n+1 so that the while loop holds
    x_next = x0+delta*20
    while abs(x_next-x_initial)>delta:
        x_initial = x_next 
        x_next = x_initial - f_prime(x_initial)/f_second_derivative(x_initial)
    return x_next

```
```python
> NR_Optimize(-10,0.001)
0.875
```
We can verify this graphically by plotting $f(x)$, a horizontal line at $y=f(x_{crit})$ and a vertical line at $x=x_{crit}$

![plot]({{"/assets/images/blog_NR_opt.png"}})

### Application to MLE

Recall that in Maximum Likelihood Estimation, our goal is to find $\theta$ such that $\ell(\theta\|data)$ is maximized. This means we can use NR for optimization in order to find the MLE $\hat{\theta}$ by doing:

$$
\theta_{n+1} = \theta_n - \frac{\ell'(\theta_n)}{\ell''(\theta_n)}
$$
