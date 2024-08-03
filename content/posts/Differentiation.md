+++
title = "Differentiation"
author = ["Zelong Kuang"]
tags = ["math", "todoist"]
draft = true
+++

---

-   Normally if without any statements, \\( f \\) is a real-valued continuous function on \\( [a,b] \\)


## Definition of differentiation {#definition-of-differentiation}

**Definition** For a function \\(f\\), defined on interval \\([a,b]\\). For \\(x \in [a,b ]\\)
\\[\lim\_{t \to x } \frac{f(t) - f(x)}{t - x} \\]
is called the differentiate of f at x, denotes by \\(f'(x)\\).

Apparently, to let \\(f'(x)\\) exists, the function has to have left/right limit (or both) at the point \\(x\\). That is, differentiable implies the function \\(f\\) is also continuous at the point.

> However, continuity does not imply the differentiability of \\(f\\) at x. If left limit at point \\(x\\) does not equal to the right limit, then \\(f'(x)\\) will have two different value for one point, which is not possible for a well-defined function.


## Calculation {#calculation}


### Basic operations {#basic-operations}

First we have to define the most basic operation, that is \\(+(-), \times, \div\\)


#### Addition {#addition}

\begin{align*}
(f + g)'(x) &= \lim\_{t \to x} \frac{(f+g)(t) - (f+g)(x)}{t-x} \\\\
&= \lim\_{ t \to x } \frac{f(t) - f(x) +g(t) - g(x)}{t - x} \\\\
&= f'(x) + g'(x)
\end{align*}


#### multiplication {#multiplication}

the idea is use 凑配法 to pairing up

\begin{align*}
fg'(x) &= \lim\_{ t \to x } \frac{fg(t) - fg(x)}{t -x} \\\\
&= \frac{f(t)(g(t) - g(x)) + g(x)(f(t) - f(x))}{ t -x } \\\\
&= f(x)g'(x) + g(x) f'(x)
\end{align*}


#### division {#division}

-   reduction method to transform to a form which is similar to the multiplication

\begin{align*}
\frac{f}{g}'(x) &= \lim\_{ t \to x } \frac{\frac{f}{g}(t) - \frac{f}{g}(x) }{t - x} \\\\
&= \lim\_{ t \to x } \frac{1}{g(t)g(x)} \left( \frac{f(t)g(x)-f(x)g(t)}{t - x} \right) \\\\
&= \lim\_{ t \to x } \frac{1}{g(t)g(x)}\left( \frac{g(x)(f(t) - f(x)) - f(x)(g(t) - g(x))}{t - x} \right) \\\\
&= \frac{f'(x)g(x) - f(x)g'(x)}{g^{2}(x)}
\end{align*}


## chain rule {#chain-rule}

this is the most important rule in calculation of differentiation.
**theorem** for function \\(f, g\\), if \\(f\\) is differentiable at \\(x\\), and \\(g\\) is differentiable at \\(f(x)\\) then for \\(h := g \circ f\\).
\\[h'(x) = g'(f(x))f'(x)\\]


## mean value theorem {#mean-value-theorem}

-   mean value theorem is a characterisation of the continuity of a function and its derivative.

there are three version of it
**lemma** let \\(f\\) defines on \\((a,b)\\) and \\(f( c)\\) is a local maximum/minimum, then \\(f'( c) = 0\\)

the derivative is greater than zero approaching from left hand side, and less than zero when approaching from right hand side, then by sandwich's theorem.


### **the** mean value theorem (lagrange) {#the-mean-value-theorem--lagrange}

**theorem** \\(f\\) are continuous on \\([a, b]\\) and differentiable on \\((a,b)\\). then
\\[f(b) - f(a) = (b - a)f'(x)\\]

> special case of generalised mean value theorem
> let g(x) = x.


### generalised mean value theorem (cauchy) {#generalised-mean-value-theorem--cauchy}

**theorem** \\(f\\) and \\(g\\) are continuous on \\([a,b]\\) and differentiable on \\((a,b)\\). then
\\[ [f(b) - f(a)]g'(x) = [g(b) - g(a)]f'(x)\\]
a geometrical interpretation is the mean value theorem for parametric function \\(x = g(t), y = f(t)\\) on \\(xy\\)-plane


#### motivation of cauchy mvt {#motivation-of-cauchy-mvt}

it generalises the mean value theorem to parametric functions.


### the continuity of derivatives {#the-continuity-of-derivatives}


#### the intermediate value theorem for derivative {#the-intermediate-value-theorem-for-derivative}

portrays the connectedness and continuity of derivative

> the difficulty of this theorem is we couldn't know the continuity of the derivative of the function (second-kind discontinuity).

**theorem** suppose \\( f \\) is a real differentaible function on \\( [a,b] \\) and suppose \\( f'(a) < \lambda < f'(b) \\) (or &gt;). then there is a point \\( x \in (a,b) \\) such that \\( f'(x) = \lambda \\).

> integrate it into \\( f \\) such that we could apply mean value theorem, because we know that \\( f \\) is continuous.


### l'hospital's rule {#l-hospital-s-rule}

**theorem** suppose \\(g'(x) \ne 0\\). if
\\[f(x) \to 0 \text{ and } g(x) \to 0 \text{ as } x \to a\\]
or if
\\[g(x) \to \infty \text{ as } x \to a\\]
then
\\[\frac{f(x)}{g(x)} = \frac{f'(x)}{g'(x)} \text{ as } x \to a.\\]


#### idea {#idea}

use cauchy mean value theorem to approach a upper bound and a lower bound of \\(\frac{f(x)}{g(x)}\\) and then use sandwich.


## taylor's theorem {#taylor-s-theorem}

> polynomial approximation of function

**theorem** suppose \\(f\\) is a real function defined on \\([a,b]\\) and \\(f^{(n-1)}\\) is continuous on \\([a, b]\\), \\(f^{(n)}\\) exists on \\((a,b)\\). for two distinct point \\(\alpha, \beta \in [a, b]\\), define

\\[p(t) = \sum\_{k=0}^{n-1} \frac{f^{(k)}(a)}{k!} (t-a)^{k}\\]

then there exists \\(x \in (\alpha, \beta )\\) such that

\\[
f(\beta) = p(\beta) + \frac{f^{(n)}(x)}{n!}(\beta-\alpha)^n\\]

the latter is called the remainder, and also be known as the error of the approximation.

> this is a consequence of mean value theorem. note that for n = 1, this is just the mean value theorem.

1.  determine the errors from the polynomial to the function.
2.  then show that this error is negligible


## vector-valued functions {#vector-valued-functions}

basically the same as dealing with 2-dimensional by letting \\(\varepsilon\\) be \\( \sqrt[n]{\varepsilon} \\). the continuity will remains according to the norm.
but mean value theorem will become weaker on n-dimensional, since the graph of \\( f \\) now has more path from one point to another point. that, we could find a point \\( x \in (a, b) \\) such that the relation becoming no longer an equal
\\[
\mathbf{f}(b) - \mathbf{f}(a) \le (b - a) \left| \mathbf{f}' (x) \right|\\]
