+++
title = "The Riemann-Stieltjes Integral"
author = ["Zelong Kuang"]
tags = ["math", "Analysis"]
draft = false
+++

## Definition and existence of integral <span class="tag"><span class="math">math</span><span class="Analysis">Analysis</span></span> {#definition-and-existence-of-integral}


### How is Riemann-integral defined? {#how-is-riemann-integral-defined}

**Definition** Let [a,b] be a given interval. For a partition \\( P \\)
\\[
a = x\_0 \le x\_1 \le \dots \le x\_{n-1} \le x\_n = b\\]
We write
\\[
\Delta x\_i = x\_i - x\_{i-1} (i = 1 , \dots ,n)\\]

Suppose \\( f \\) is bounded real function defined on \\( [a, b] \\). Now with in each section \\( [x\_{i-1}, x\_{i}]\\), there exists upper bound and lower bound, put

\begin{align\*}
M\_i &= \sup\_{} f(x) (x\_{i-1} \le x \le x\_{i}) \\\\
m\_i &= \inf\_{} f(x) (x\_{i-1} \le x \le x\_{i})
\end{align\*}

Then, for a fine partition, the area of \\( f \\) could be approximated with many rectangles.

\begin{align\*}
U(P,f) &= \sum\_{i = 1}^n M\_i \Delta x\_i \\\\
L(P,f) &= \sum\_{i = 1}^n m\_i \Delta x\_i \\\\
L(P,f) & \le Area(f) \le U(P,f)
\end{align\*}

And, finally we define

\begin{equation}
\overline{\int\_{a}^{b}} f \text{d}x = \inf\_{} U(P,f),
\end{equation}

\begin{equation}
\underline{\int\_a^{b}} f \text{d} x = \sup\_{} L(P,f)
\end{equation}

where inf and sup are taken over all partitions \\( P \\). The equation (1) and (2) are called the **upper** and **lower** Riemann integrals of \\( f \\) respectively.

If they are equal, we say that \\( f \\) is _Riemann-integrable_ on \\( [a,b] \\), we write \\( f \in \mathcal{R} \\), and \\( (1) = (2) = \int\_a^b f(x) \text{d}\alpha(x) \\).

---

**Definition** \\( P^{\*} \\) is called the refinement of \\( P \\). Put it in simple, it cuts more on the basis of \\( P \\).

**Theorem**. A partition with finer partition is more accurate, that is

\begin{align\*}
  L(P,f,a) &\le L(P^{\*},f,a) \\\\
  U(P^{\*},f,a) &\le U(P,f,a)
\end{align\*}

This theorem is quite obvious. Just consider one of the extra points: \\( x\_i \in (x\_j, x\_{k}) \\). Clearly, \\( m\_{i} \le \inf\_{}f(x)  \\) for \\( x \in (x\_j, x\_i) \cup (x\_i, x\_{k}) \\).

**Theorem**
\\[
\overline{\int\_a^b} f dx= \underline{\int\_{a}^b} f dx\\]

We always have \\( \inf\_{} f(x) \le \sup\_{} f (x)  \\) for \\( x \\) within any interval

**Theorem** \\( f \\) is riemann integrable if and only if \\( U(P,f,a) \\) is closed enough to \\( L(P,f,a) \\), that is, \\( U(P,f,a) - L(P,f,a) < \varepsilon \\) forall \\( \varepsilon >0 \\)

\\( f \\) is riemann integrable if and only if \\( \inf\_{} U = \sup\_{} L   \\)

**Theorem**
(a) If the inequality above holds for some partition, then it also holds for every refinement of \\( P \\).
Note: Corollary of

\begin{align\*}
  L(P,f,a) &\le L(P^{\*},f,a) \\\\
  U(P^{\*},f,a) &\le U(P,f,a)
\end{align\*}

(b) If ... holds for P, then for any \\( s\_i, t\_i \in [x\_{i-1}, x\_{i}] \\), the same equality holds even if replace \\( x\_{i} \\) with \\( s\_i \\) and \\( t\_{i} \\).
Note: We always have \\( \inf\_{} f(x) \le f(x) \le \sup\_{} f (x)  \\) for any \\( x \\) in a partition.

(c) If \\( f \\) is Riemann-integrable, then the same holds for the area approximation and \\( \int f \\)

**Theorem** If \\( f \\) is continuous, then \\( f \\) is Riemann-Integrable.

Note: Just choose the partition to be the \\( \delta > 0 \\), then continuity will show that \\( \Delta f < \varepsilon \\).

**Theorem** If \\( f \\) is monotonic and \\( \alpha \\) (assumed to be monotonic) is continuous, then \\( f \\) is Riemann-Integrable.

**Theorem** If \\( f \in \mathcal{R}(\alpha)\\), and \\( g \\) is continuous. Then \\( g(f(x)) \in \mathcal{R}(\alpha)\\)

Note:

**Theorem** If \\( f, g \in \mathcal{R}(\alpha)\\) then

-   \\( fg \in \mathcal{R}(\alpha) \\)
-   \\( |f| \in \mathcal{R}(\alpha) \\)


### \*[Vector-valued functions]({{< relref "../20240809-vector_valued_functions.md" >}}) {#vector-valued-functions--dot-dot-20240809-vector-valued-functions-dot-md}

**Definition** Like differentiation, we integrate each component separately,
\\[
\int \mathbf{f} d\alpha = \int(f\_1 + \dots + f\_k)d\alpha\\]
