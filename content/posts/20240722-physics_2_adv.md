+++
title = "Physics 2 adv. lecture note"
author = ["Zelong Kuang"]
tags = ["Electromagnetic", "Physics"]
draft = false
+++

## Electromagnetism {#electromagnetism}


### Electric Force {#electric-force}

-   Net force: \\( \vec{F\_{R}} = \vec{F}\_{1 \text{ on } q} + \vec{F}\_{2 \text{ on } q} + \dots\\)

Electric force is similar to the gravitational but varies inversely, like \\( \lim x \text{ and } \lim \frac{1}{x} \\)

Unlike there is only attaction in gravitation, electrical has repulsion.


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

    This is hard to integrate at this point. To solve we can use trig to transform z, r in \\( \theta, x\\) (or opposite).

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

<!--list-separator-->

-  Repeating Coulomb's Experiment

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

Similarly, we evaluate its derivative
\\[
d\vec{E} = k\_e \frac{\text{d} q}{r ^2} = k\_e \frac{\lambda d z}{r ^2}\\]
And then its integral

From horizontal symmetry,
\\[
\vec{E} = \int d\vec{E} \cos \theta
\\]
Here,

\begin{align\*}
r ^2 &= z ^2 = R ^2 \\\\
\cos \theta &= \frac{z}{r} = \frac{z}{\sqrt{z ^2 + R ^2}}
\end{align\*}

And so

\begin{align\*}
\vec{E} &= \int d\vec{E} \cos \theta \\\\
&= k\_e \frac{1}{z ^2 + R ^2} \frac{z}{\sqrt{z ^2 + R ^2}} \int\_{\mathrm{ring }}dQ \\\\
&= k\_e \frac{Qz}{(z ^2 + R ^2 )^{3/2}}
\end{align\*}


#### Dipole moment {#dipole-moment}

\\[|\vec{p}|  = qd\\]

-   in the direction from -ve to + ve charge.


#### Why do we use electric field? {#why-do-we-use-electric-field}

If we know the electric field at any point we can
immediately calculate the force it will apply to any
arbitrary charge, q, placed at that point.


#### Torque experienced in an electric field <span class="tag"><span class="ATTACH">ATTACH</span></span> {#torque-experienced-in-an-electric-field}

\begin{align\*}
  \vec{\tau} &= \vec{r} \vec{F} \\\\
  \vec{F} &= \vec{E} q \\\\
\end{align\*}

{{< figure src="/ox-hugo/Screenshot 2024-07-30 at 10.31.56 PM.png" width="500px" >}}

\begin{align\*}
\implies \vec{\tau} &= -\vec{d}\vec{E}q \sin \theta \\\\
&= -q \vec{d} E \sin \theta \\\\
&= |\vec{p}| \vec{E}
\end{align\*}


#### Gauss' Law {#gauss-law}

-ve on in going
+ve on out going

The body of **Gauss' law** is the equation:

\\[
\Phi = \oint \vec{E} d\vec{A}\\]

For different shapes, the electric field lines passed through are different resulting in different \\( \Phi  \\).
The followings are some common shapes which we might often meet.

Could also be applied to other _fields_, for example, gravitational field

<!--list-separator-->

-  Sphere

    Following from Gauss' law, we have,

    \begin{align\*}
     \vec{E} \oint\_{\text{sphere}} d\vec{A} &= \frac{q}{\varepsilon\_{0}} \\\\
      \vec{E} 4 \pi r ^2 &= \frac{q}{\varepsilon\_{0}} \\\\
      E &= k\_e \frac{q}{r ^2}
    \end{align\*}

<!--list-separator-->

-  Cylinder

    <!--list-separator-->

    -  Vertical aligned

        For a vertical cylinder,

        \\[ \vec{E}\oint d\vec{A} = \frac{q\_{enclosed}}{\varepsilon\_{0}} \\]
        Because the top and bottom circle area are paralleled to the electric field, so we could ignore them. So, we have,
        \\[
        \vec{E} 2 \pi r h = \frac{q\_{enclosed}}{\varepsilon\_{0}}
        \\]
        Notice here, we could replace \\( q\_{enclose} \\) with \\( \lambda h \\), then

        \begin{align\*}
        \vec{E} 2\pi r h &= \frac{\lambda h}{\varepsilon\_{0}} \\\\
        \vec{E} &= k\_e \frac{2\lambda}{r}
        \end{align\*}

        We could generalise the equation,
        \\[
        \vec{E} = k\_e \frac{\lambda \theta}{r}\\]

        <!--list-separator-->

        -  Can we replace &lambda; with &sigma; ?

            Maybe, but the key difference is the electric field is passing through a curved surface in this situation, whereas the horizonal one is a flat surface.

    <!--list-separator-->

    -  Horizontal aligned <span class="tag"><span class="ATTACH">ATTACH</span></span>

        {{< figure src="/ox-hugo/Screenshot 2024-07-31 at 1.03.38 PM.png" width="500px" >}}

        -   \\( \sigma (c \cdot m ^{-2}) \\) sheet of charge (charge on that sheet)

        From the flux from two end of the cylinder, we get

        \begin{align\*}
        EA + EA &= \frac{\sigma A}{\varepsilon\_{0}} \\\\
        E &= \frac{\sigma}{2 \varepsilon\_{0}}
        \end{align\*}

    <!--list-separator-->

    -  An charged partitle in electric field

        {{< figure src="/ox-hugo/a.drawio.svg" >}}

        \\[
        \Delta t = \frac{L}{v\_{x}}\\]

        For a electron passing through a electric field, because it is only experiencing the field force, so we have

        \begin{align\*}
        F = Eq &= ma \\\\
        \implies a &= \frac{Eq}{m} \\\\
        \Delta y &= \frac{1}{2} (\frac{Eq}{m}) (t ^2) \\\\
        &= \frac{1}{2} \frac{Eq}{m} \frac{L^2}{v\_x^2}
        \end{align\*}

<!--list-separator-->

-  Asymmetric

    At the mid point of two positive,
    \\[
    EA - EA  = 0\\]

    -   Principle of Faraday's cage

    Will terminate inside somewhere, symetrically cancelled out(?).
