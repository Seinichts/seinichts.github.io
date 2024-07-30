+++
title = "Physics 2 adv. lecture note"
author = ["Zelong Kuang"]
tags = ["Electromagnetic", "Physics"]
draft = false
+++

## Electromagnetism {#electromagnetism}


### Electric Force {#electric-force}

-   Net force: \\( \vec{F\_{R}} = \vec{F}\_{1 \text{ on } q} + \vec{F}\_{2} \text{ on } q + \dots\\)

Electric force is similar to the gravitational but varies inversely, like \\( \lim x \text{ and } \lim \frac{1}{x} \\)

Unlike there is only attaction in gravitation, electrical has repulsion  :Electromagnetic:Physics:


### Electric charge {#electric-charge}


#### Coulomb's law {#coulomb-s-law}

\\[
F = k\_e \frac{q\_1q\_2}{r ^2} \vec{\mathbf{r}}\\]

Note:\\( k\_e  = \frac{1}{4 \pi \epsilon\_{0}} \sim 8.99\* 10 ^{9} \\) and \\( \vec{r} \\) is the unit vector on **the** direction.

> Similar to Gravitational force
> \\[
> F = G \frac{M\_{1}M\_2}{r ^2}\\]

We take differentiation for one of the \\( q\_{i} \\), that is
\\[
dF = k\_e \frac{q\_1 \text{d} q\_2}{r ^2} = k\_e \frac{q\_1 \lambda d z}{r ^2}\\]

-   z-axis: line of charge

The last equal sign follows from the linear charge density \\( \lambda \\)(\\( C m^{-1} \\)): dz = \\( \lambda \\) dq at "\\( dz \\)".

<!--list-separator-->

-  Evaluation of integration

    By first, following from the image above, we could see that every charge at z-axis has a corresponding charge in the opposite direction performing cancellation. Such that

    \begin{align\*}
    \vec{F}\_R &= \int d\vec{F}\_{x} \\\\
    &= \int d\vec{F}\_{dq} \cos \theta \\\\
    &= \int  k\_e \frac{q\_1 \lambda dz}{r ^2} \cos \theta
    \end{align\*}

    This is too hard to integrate at this point. To solve we can use trig to transform z, r in \\( \theta, x\\) (or opposite).

    \\[
    \cos \theta = \frac{x}{r} \implies \frac{1}{r ^2} = \frac{\cos ^2 \theta}{x ^2}\\]

    \\[
    \tan \theta = \frac{z}{x} \implies z = x \tan \theta \implies dz = x \sec ^2 \theta d\theta\\]

    Therefore,

    \begin{align\*}
    \vec{F}\_R &= \int k\_{e} \frac{q\_1 \lambda x \sec ^2 \theta \cos ^2 \theta d\theta}{x ^2} \cos \theta \\\\
    &= \frac{k\_e q\_{1}\lambda}{x} \int\_{-\pi/2}^{\pi/2} \cos \theta d\theta \\\\
    &= \frac{2k\_eq\_1\lambda}{x} = \frac{1}{2 \pi \epsilon\_0} \frac{q \lambda}{x}
    \end{align\*}


#### Repeating Coulomb's Experiment {#repeating-coulomb-s-experiment}

{{< figure src="/Users/zelong/Desktop/Screenshot 2024-07-27 at 8.28.19 PM.png" >}}

There is two identical balls hanging with silk thread which have a metallised surface.

From the following formula deduction:

\begin{equation}
\label{eq:1}
mg = \tau \cos \theta \implies \tau = \frac{mg}{\cos \theta}
\end{equation}

\begin{equation}
\label{eq:2}
F\_{Q1} = \tau \sin \theta = mg \tan \theta = mg\frac{r\_1 / 2}{\sqrt{\ell\_2 - (\frac{r\_1}{2})^2}} = \frac{mgr\_1}{\sqrt{4\ell\_2 - r\_1 ^2}}
\end{equation}

Then, suppose two balls, initially, are charged with \\( Q\_{1} \\). If we halve the charge in one of them, we will get a new radius, called \\( r\_2 \\), and so \\( F\_2 \\) from the equation above.

If we keep repeating this process, we could get a list of data.

But before that, from [Coulomb's law](#coulomb-s-law), we know that

\begin{equation}
F = \frac{1}{4\pi\varepsilon\_0} \frac{(1 \times 10 ^{-8}) ^2}{r\_1 ^2} = \frac{mg r\_1}{\sqrt{4\ell\_2} - r\_1 ^2}
\end{equation}


### Electric Field {#electric-field}

**Electric field** defined as force per unit <span class="underline">positive</span> charge.
\\[
\vec{E} = \frac{\vec{F}}{q} (\text{Units: } N.C ^{\text{-}1} \text{ or } V.m ^{\text{-}1})\\]

or
\\[
\vec{E} = k\_e\frac{q}{r ^2}\\]

-   [Gauss's law]({{< relref "20240729-gauss_s_law.md" >}})
