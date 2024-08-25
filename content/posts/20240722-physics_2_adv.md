+++
title = "Physics 2 adv. lecture note"
author = ["Zelong Kuang"]
tags = ["Electromagnetic", "Physics"]
draft = false
+++

## Electromagnetism {#electromagnetism}


### Electro {#electro}


#### Electric Force {#electric-force}

-   Net force: \\( \vec{F\_{R}} = \vec{F}\_{1 \text{ on } q} + \vec{F}\_{2 \text{ on } q} + \dots\\)

Electric force is similar to the gravitational but varies inversely,
like \\( \lim x \text{ and } \lim \frac{1}{x} \\)

Unlike there is only attaction in gravitation, electrical has repulsion.

-   Electrostatic force: \\( F = q \vec{E} \\)


#### Electric charge {#electric-charge}

<!--list-separator-->

-  Coulomb's law

    \\[
    F = k\_e \frac{q\_1q\_2}{r ^2} \vec{\mathbf{r}} = q\vec{E}\\]

    Note:\\( k\_e  = \frac{1}{4 \pi \epsilon\_{0}} \sim 8.99\* 10 ^{9} \\) and \\( \vec{r} \\) is the unit vector on **the** direction.

    Similar to Gravitational force
    \\[
    F = G \frac{M\_{1}M\_2}{r ^2}\\]

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
        mg = \tau \cos \theta \implies \tau = \frac{mg}{\cos \theta}
        \end{equation}

        \begin{equation}
        F\_{Q1} = \tau \sin \theta = mg \tan \theta = mg\frac{r\_1 / 2}{\sqrt{\ell\_2 - (\frac{r\_1}{2})^2}} = \frac{mgr\_1}{\sqrt{4\ell\_2 - r\_1 ^2}}
        \end{equation}

        Then, suppose two balls, initially, are charged with \\( Q\_1 \\). If we halve the charge in one of them, we will get a new radius, called \\( r\_2 \\), and so \\( F\_2 \\) from the equation above.

        If we keep repeating this process, we could get a list of data.

        But before that, from [Coulomb's law](#coulomb-s-law), we know that

        \begin{equation}
        F = \frac{1}{4\pi\varepsilon\_0} \frac{(1 \times 10 ^{-8}) ^2}{r\_1 ^2} = \frac{mg r\_1}{\sqrt{4\ell\_2} - r\_1 ^2}
        \end{equation}


#### Electric Field {#electric-field}

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

<!--list-separator-->

-  Electric Dipole moment

    \\[|\vec{p}|  = qd\\]

    -   in the direction from -ve to + ve charge.

<!--list-separator-->

-  Why do we use electric field?

    If we know the electric field at any point we can
    immediately calculate the force it will apply to any
    arbitrary charge, q, placed at that point.

<!--list-separator-->

-  Torque experienced in an electric field <span class="tag"><span class="ATTACH">ATTACH</span></span>

    \begin{align\*}
      \vec{\tau} &= \vec{r} \vec{F} \\\\
      \vec{F} &= \vec{E} q \\\\
    \end{align\*}

    {{< figure src="/ox-hugo/Screenshot 2024-07-30 at 10.31.56 PM.png" width="500px" >}}

    \begin{align\*}
    \implies \vec{\tau} &= -\vec{d}\vec{E}q \sin \theta \\\\
    &= -q \vec{d} E \sin \theta \\\\
    &= |\vec{p}| \vec{E} \sin \theta
    \end{align\*}

<!--list-separator-->

-  Gauss' Law

    -ve on in going
    +ve on out going

    The body of **Gauss' law** is the equation:

    \\[
    \Phi = \oint \vec{E} d\vec{A} = \frac{q\_{enclosed}}{\varepsilon\_{0}}\\]

    One important statement from the equation is: **the Gaussian surface of a Gaussian sphere doesn't "increase" in the sense that its surface area increases; the flux remains the same between analogous gaussian shape**. That is, the quantity of the flux doesn't matter of the size.

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

            **NOTE THAT:** The cylinder here has finite length; A super-long cylindrical wire has to discuss separately from this case.

        <!--list-separator-->

        -  An charged partitle in electric field

            {{< figure src="/ox-hugo/a.drawio.svg" width="500px" >}}

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

    -  symmetric

        At the mid point of two positive,
        \\[
        EA - EA  = 0\\]

        -   Principle of Faraday's cage

        Will terminate inside somewhere, symetrically cancelled out(?).


#### Potential energy {#potential-energy}

Displacement will create change in potential energy, from [Torque experienced in an electric field](#torque-experienced-in-an-electric-field), we have
\\[
d U = qE \sin \theta d\theta\\]
Thus,
\\[
\Delta U = - qE \cos \theta |\_{\theta\_{i}}^{\theta\_{f}}\\]


#### Voltage {#voltage}

Aka, Potential difference.

Voltage is defined as potential difference per charge.

<!--list-separator-->

-  Continuous charge distribution

    For a single charge (isolated charge):

    \\[
    V = k\_e \frac{q}{r}\\]

    <!--list-separator-->

    -  Differentiate against r

        Which gives that
        \\[
        dV = k\_e \frac{-q}{r ^2}dr\\]
        and thus,
        \\[
        V = k\_e \int \frac{-q}{r ^2} dr\\]

        Alternatively, we could also

    <!--list-separator-->

    -  Differentiate against q <span class="tag"><span class="ATTACH">ATTACH</span></span>

        Such that,
        \\[
        dV = k\_e \frac{dq}{r}\\]
        \\[
        V = k\_e \int \frac{dq}{r}\\]

<!--list-separator-->

-  Electrostatic potential due to dipole

    For a dipole, the potential difference at a random-choose point P is given by

    \begin{align\*}
    V\_P &= k\_e[\frac{q}{r\_+} - \frac{q}{r\_{-}}] \\\\
    &= k\_e q \frac{r\_ -- r\_+}{r\_+r\_-}
    \end{align\*}

    <!--list-separator-->

    -  Special case: when r is large enough <span class="tag"><span class="ATTACH">ATTACH</span></span>

        At local, \\( r\_- - r\_+ \sim  s \cos\theta \\), substitude it into the equation above will give:
        \\[
        V\_P = k\_eq \frac{s\cos\theta}{r ^2}
        \\]
        Following from [Dipole moment](#electric-dipole-moment)
        \\[
        V\_p = k\_e \frac{p\cos\theta}{r ^2}\\]

    <!--list-separator-->

    -  On a thick positively charged rod <span class="tag"><span class="ATTACH">ATTACH</span></span>

        \begin{align\*}
        V\_P &= k\_eq \int\_0^L \frac{dl}{\sqrt{d ^2 + l ^2 }} \\\\
        &= k\_e q \ln(l ^2 + \sqrt{d ^2 + l ^2 })|\_0^{L} \\\\
        &= k\_e q \ln(\frac{l^2+\sqrt{d ^2 + l ^2 }}{d})
        \end{align\*}

    <!--list-separator-->

    -  Cone

        To calculate the voltage of point p which locates above the center of a circle (they form a cone shape)

        \\[
        V = k\_e \int \frac{dq}{r}\\]
        Here
        \\[
        dq = \sigma dA\\]
        Substitution gives that,
        \\[
        V = k\_e \int \frac{\sigma dA}{r}\\]
        And similar to example above, we get

        \begin{align\*}
         V\_P &= k\_e \sigma \int\_0^L \frac{x dx}{\sqrt{d ^2 + x ^2 }} \\\\
         &= k\_e \sigma \sqrt{d ^2 + x ^2 }|^L\_{0} \\\\
         &= k\_e \sigma (\sqrt{d ^2 + l ^2 } - d)
        \end{align\*}


#### Capacitors <span class="tag"><span class="ATTACH">ATTACH</span></span> {#capacitors}

{{< figure src="/ox-hugo/Screenshot 2024-08-24 at 4.51.18 PM.png" width="200px" >}}

For capacitors: \\( q = CV \\).

But also, by [Gauss' Law](#gauss-law), we also know that
\\[
V = Ed = \frac{qd}{\varepsilon\_{0}A}\\]
This implies that
\\[
C = \frac{q}{V} = \frac{\varepsilon\_0A}{d}\\]

Moreover,
\\[
U = \frac{1}{2} q V = \frac{1}{2} C V ^2
\\]
We can substitude the variation above to make it to be a equation contain `q and d only`.
\\[
U = \frac{q ^2 d}{2 \varepsilon\_{0}A}\\]
or `E and D`:
\\[
U = \frac{1}{2} qEd = \frac{1}{2} \varepsilon\_{0}Ad E ^2 \\]

-   Ad: the volume between two capacitor plates.


#### Dieletrics {#dieletrics}


#### Circuit {#circuit}

<!--list-separator-->

-  [Capacitors](#capacitors) in circuit

    <!--list-separator-->

    -  Parallel <span class="tag"><span class="ATTACH">ATTACH</span></span>

        For two capacitors in parallel,

        {{< figure src="/ox-hugo/Screenshot 2024-08-24 at 5.17.39 PM.png" width="500px" >}}

        Voltage is the same throughout both capacitor, such that
        \\[
        q\_1 = C\_1 V \hspace{20px} q\_{2} = C\_{2} V\\]
        Since \\( q = q\_1 + q\_2 \\), we get \\( C = C\_{1} + C\_{2} \\). This can be generalised.

    <!--list-separator-->

    -  Series <span class="tag"><span class="ATTACH">ATTACH</span></span>

        For two capacitors in series,
        <img src="/ox-hugo/Screenshot 2024-08-24 at 5.21.07 PM.png" alt="Screenshot 2024-08-24 at 5.21.07 PM.png" width="200px" />
        we know the voltage adds up, so
        \\[
        V = \Sigma V\_{i} = \Sigma \frac{q}{C\_{i}}\\]
        We get
        \\[
        \frac{1}{C} = \sum\_{}^{}\frac{1}{C\_{i}}\\]

<!--list-separator-->

-  Conservation of energy

    -   Voltage in circuit will be distributed thoroughly. Proportional to the resistance of each resistor.

<!--list-separator-->

-  Current density

    \\( J = \frac{di}{dA} \implies i = \int J dA\\)

<!--list-separator-->

-  Ohm's Law

    \\[
    V = IR\\]


### Magnetism {#magnetism}

Magnetism is due to an interaction between moving charges.


#### Magnetic force <span class="tag"><span class="ATTACH">ATTACH</span></span> {#magnetic-force}

\\[
F = q \vec{v} \times \vec{B}\\]
Compare to [Electric Force](#electric-force) (\\( \vec{F} = q \vec{E} \\)), \\( \vec{E} = \vec{v} \times \vec{B} \\)

{{< figure src="/Users/zelong/Library/CloudStorage/OneDrive-Personal/orgnotes/Screenshot 2024-08-24 at 6.51.45 PM.png" width="300px" >}}


#### Magnetic flux {#magnetic-flux}

For magnetic flux through a closed surface, we could refer to [Gauss' Law](#gauss-law) that,
\\[
\Phi\_{B} = \oint \vec{B} d \vec{S}\\]

-   \\( \vec{B} \\) is magnetic field and can adds up (superposition).


#### Magnetic field {#magnetic-field}

<!--list-separator-->

-  Biot-Savart law <span class="tag"><span class="ATTACH">ATTACH</span></span>

    For a single charge,
    \\[
    \vec{B} = \frac{\mu\_0}{4\pi} \frac{q}{r ^2} (\vec{v} \times \vec{r})\\]

    -   Permeability constant: \\( \mu\_0 = 4\pi \times 10^{-7} TmA^{-1} \\)

    However, we are more often to deal with current, by \\( i = \frac{dq}{dt} \\),

    {{< figure src="/ox-hugo/Screenshot 2024-08-25 at 7.29.49 PM.png" width="300px" >}}

    -   \\( dl = v dt \\)

    \begin{align\*}
    d\vec{B} &= \frac{\mu\_0}{4\pi} \frac{dq}{r ^2} (\vec{v} \times \vec{r}) \\\\
    d\vec{B} &= \frac{\mu\_0}{4\pi} \frac{idt}{r ^2} (\frac{dl}{dt} \times \vec{r}) \\\\
    &= \frac{\mu\_{0}}{4\pi} \frac{id\vec{l} \times \vec{r}}{r ^2}
    \end{align\*}

<!--list-separator-->

-  Magnetic dipole moment

    \\[
    \mu\_B = i \times (\text{area of loop})\\]

    -   Dipole moment for electrons: \\( (\mu\_{B})\_{e} = 9.3 \times 10 ^{-24} A.m^2\\)

<!--list-separator-->

-  Ampere's Law

    Ampere's Law take the same place as what [Gauss' Law](#gauss-law) is in electrostatics.

    \\[
    \oint \vec{B} \cdot d\vec{l} = \mu\_0 i\_{\text{enclosed}}\\]
