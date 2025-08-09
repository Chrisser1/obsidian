Lad $f,g: I \to \mathbb{R}$, $I \in \mathbb{R}$, være hhv $c^0$   og $c^1$-funktioner. 

![[Pasted image 20250318111346.png]]
![[Pasted image 20250318111357.png]]

#### Ex. Find en stamfunktion til $h(x)=xe^{3x}, \quad x \in \mathbb{R}$.
Vi skal altså udregne:
$$
\int xe^{3x} dx= ?
$$
Vi kan nu opskrive de forskellige led
$$
g(x)=x, \quad f(x)=e^{3x}, \quad F(x) \frac{1}{3}e^{3x}
$$
Vi får nu stamfunktionen 
$$
\int xe^{3x} = \frac{1}{3}e^{3x} \cdot x - \int  \frac{1}{3}e^{3x} dx = \frac{1}{3}e^{3x} \cdot x - \frac{1}{3}\frac{1}{3}e^{3x} = \frac{1}{3}e^{3x} \cdot x - \frac{1}{9}e^{3x} = \frac{1}{3}e^{3x} - (x - \frac{1}{3})
$$

#### Eksempel 2: substitution

Vi ønsker at løse følgende integral:
$$
\int \frac{1}{1 - 2x} \,dx, \quad x \neq \frac{1}{2}
$$
Vi ved fra integralregning, at:
$$
\int \frac{1}{x} \,dx = \ln |x|, \quad x \neq 0
$$
Dette minder om vores udtryk, men nævner ikke koefficienten $-2x$ i nævneren.

**Substitution**

Lad os definere en substitution:

$$

u = g(x) = 1 - 2x

$$

Vi differentierer $g(x)$:

$$

g'(x) = -2

$$

Vi genkender nu, at vores funktion kan omskrives med substitution.

**Omskrivning af integralet**

Vi skriver integralet om:

$$

\int \frac{1}{1 - 2x} \,dx = -\frac{1}{2} \int \frac{1}{1 - 2x} (-2) \,dx

$$

Ved at introducere og multiplicere med $-2$ kan vi forberede os på substitution.

Når vi sætter $u = 1 - 2x$, ser vi, at:

$$

du = -2dx

$$

Derfor omskrives integralet:

$$

-\frac{1}{2} \int \frac{1}{u} \,du

$$

**Beregning  af integralet**

Vi kender standardintegralet:

$$

\int \frac{1}{u} \,du = \ln |u|

$$

Så vi får:

$$

-\frac{1}{2} \ln |u|

$$

Indsætter vi tilbage for $u = 1 - 2x$, får vi det endelige resultat:

$$

-\frac{1}{2} \ln |1 - 2x|

$$

**Differentiabilitet af $u(x)$**

Til sidst noterer vi os, at:

$$

\frac{du}{dx} = u'(x) = -2

$$

og at differentialet af $u(x)$ ifølge definition 3.8.2 er:
$$
df_{x_0} = 1
$$
