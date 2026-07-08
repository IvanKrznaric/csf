# Long Time Behaviour

:::{prf:theorem} @MR840401, @MR906392
:label: gage-hamilton-grayson

The CSF exists on the maximal time interval $[0, T)$ where $T = \tfrac{A_0}{2\pi}$ where $A_0$ is the initial area. Upon rescaling to fix the total length, the CSF converges smoothly to a circle of total length $L_0$ as $t \to T$ where $L_0$ is the initial length.
:::

A useful place to find information about the theorem is the [Wikipedia article on CSF](https://en.wikipedia.org/wiki/Curve-shortening_flow#Gage%E2%80%93Hamilton%E2%80%93Grayson_theorem).

The presentation of the proof follows the proof from [this book](https://doi.org/10.1090/gsm/206) by Andrews, Chow, Guenther and Langford.

## Intuition, motivation

## Huisken's distance comparison

One of the very important properties of the curve shortening flow in the plane is that the embeddedness is preserved during the flow. One way such a result can be stated is in the following form.

:::{danger} Theorem
:icon: false
Let $X : [0, t_0] \times \mathbb{S}^1 \rightarrow \mathbb{R}^2$ be a solution to the curve shortening flow. If $X(0, \cdot)$ is an embedding, then $X(t, \cdot)$ is an embedding for all $t \in [0, t_0]$.
:::

The proof of the theorem goes along the following lines : since $\mathbb{S}^1$ is compact,  in order to prove embeddedness it is enough to show that $X(t, \cdot)$ is injective. In order to prove injectivity, we define the function

\begin{equation*}
d(t,x,y) = \lvert X(t, y) - X(t,x) \rvert,
\end{equation*}

and we wish to show that $d$ is bounded from below by a positive constant. Such a lower bound can be shown using the maximum principle and curvature bounds (here we use the fact that we are working on a time interval of the form $[0, t_0]$).

Therefore, it is apparent that the theorem above heavily relies on the curvature bounds along the flow, and that's also why the time interval is required to be of the form $[0, t_0]$. In some sense, this is a "short-time" result. If we are interested in long time behaviour of the curve shortening flow, a new approach is needed -- since the extinction time $T$ of the flow is characterized by

\begin{equation*}
\limsup_{t \to T} \max_{\Gamma_t} \kappa = + \infty,
\end{equation*}

we are unable to use the curvature bounds to bound the distance $d$ using the same methods, and so we need to bound $d$ in some other way. This new approach to obtaining the said bounds is due to G. Huisken.

In order to see what form of a bound we are looking for, we are going to consider one of the nicest solutions to the curve shortening flow - the shrinking circle. Looking at the figure below, and using the basic trig identities, it follows that for all points $x,y$ on the circle we have

\begin{equation*}
\label{eqn-trig}
d = \frac{L}{\pi} \sin \left( \frac{\pi l}{L} \right),
\end{equation*}

where $d$ is the chord-distane between $x$ and $y$, the arc-length between those two points is denoted by $l$, and $L$ is the circumference of the circle. In other words, the quantity

\begin{equation*}
Z = \frac{L}{d} \sin \left( \frac{\pi l}{L} \right)
\end{equation*}

is constant on the circle and has the value of $\pi$. This motivates us that, given the solution $X = X(t,x)$ of the curve shortening flow, we consider the function $Z :  \left[ 0,T \right> \times \left( \mathbb{S}^1 \times \mathbb{S}^1 \setminus \left\{ (x,x) : x \in \mathbb{S}^1 \right\} \right) \rightarrow \mathbb{R}$ defined by

\begin{equation*}
Z(t,x,y) \coloneqq \frac{L(t)}{d(t,x,y)} \sin \left( \frac{\pi l(t,x,y)}{L(t)} \right),
\end{equation*}

where $d, l, L$ denote, respectively, the chord distance, the arc-length and the total length of the curve $X(t, \cdot)$.

Now the goal is to somehow control the values $Z$ attains -- suppose that a singularity was about to form at some time $t$ before the extinction time, i.e. $t < T$. Then somewhere along the curve, we whould have some points $x$ and $y$ such that the chord-distance $d$ would be very small, and since the curve hasn't shrinked to a point just yet, we would have

\begin{equation*}
\sup Z \geq \frac{L(t)}{d(t,x,y)} \sin \left( \frac{\pi l(t,x,y)}{L(t)}\right) \to \infty
\end{equation*}

and so the supremum of $Z$ would be unbounded. Hence, if we manage to somehow get a handle on the values $Z$ attains, we can rule out the possibility of a singularity forming before extinction time, and hence concluding that embeddedness is preserved. Then following theorem tells us that this is the case, provided that we have an embedding at $t = 0$.

:::{danger} Theorem (Huisken)
:icon: false
:label: thm-huisken
Let $X : [0, T \rangle \times \mathbb{S}^1 \rightarrow \mathbb{R}^2$ be a solution of the curve shortening flow such that $X(0, \cdot)$ is an embedding. Then $\sup \left\{ Z(t,x,y) : x,y \in \mathbb{S}^1 \right \}$ is non-increasing in time.
:::

## Curvature bounds via distance comparison

Recall that Gage-Hamilton-Grayson's theorem states that, in particular, the curve shortening flow of an embedded curve continues to exists as long as the total length of the curve is positive. We know that the extinction time of the flow is characterized by

\begin{equation*}
\limsup_{t \to T} \max_{\Gamma_t} \kappa = + \infty,
\end{equation*}

so one possible way forwards is to obtain bounds on curvature that hold as long as the total length of the curve is positive. 

Curvature bounds can be obtained from the chord-distance $d$ - suppose that there is a point on the curve at which the curvature $\kappa$ is large. Around that point, the curve looks like a part of a circle with radius $1 / \kappa$. According to the [identity on the circle](#eqn-trig) we have computed before, we have the following approximation:

\begin{equation*}
d \approx \frac{2}{\kappa} \sin\left( \frac{\kappa l}{2} \right) \approx l - \frac{\kappa^2 l^3}{24},
\end{equation*}

where in the last line we have approximated the sine function with its degree $2$ Taylor polynomial. The main point of this simple approximation is that a large curvature can tell us something about the chord-distance. Motivated by this, let's suppose that we have a lower bound on the chord-distance of the form

\begin{equation*}
d(x,y) \geq \varphi(l(x,y)),
\end{equation*}

where $x,y$ are two points on the curve and $\varphi(x)$ satisfies

\begin{equation*}
\varphi(x) \geq x - Cx^3 + o(x^5)
\end{equation*}

for small $x$, i.e. $x \approx 0$. If such a bound were to hold, then we could control the curvature since given two points $x,y$ with $l(x,y) \approx 0$, we would have

\begin{equation*}
\begin{split}
l - \frac{\kappa^2 l^3}{24} \approx d & \geq \varphi(l(x,y)) \geq l - C l^3 \\
\implies \kappa^2 & \leq 24C
\end{split}
\end{equation*}

so we would have a global control over the curvature. Therefore, the next thing we have to do is to obtain a lower-bound on $d$ of the form above.

Let's note that we already know of at least one bound of the form $d \geq \varphi(l(x,y))$ and that's the bound from [Huisken's distance comparison](#thm-huisken): it can be shown that the supremum at time $t = 0$ is greater than $\pi$ so there exists some $n \in \mathbb{N}, n \geq 2$ such that $\sup \{Z(0,x,y) : x,y \in \mathbb{S}^1 \} \leq n\pi$, and since the supremum is non-increasing it follows that

\begin{equation*}
\begin{split}
& Z \leq \sup \{Z(0,x,y) : x,y \in \mathbb{S}^1 \} \leq n\pi \\
\implies & \frac{L}{d} \sin \left( \frac{\pi l}{L} \right) \leq n \pi \\
\implies & d \geq \frac{cL}{\pi}\sin\left( \frac{\pi l}{L} \right),
\end{split}
\end{equation*}

where we have denoted $c \coloneqq 1/n \in \langle 0,1 \rangle$. If we define $\varphi(x) \coloneqq \frac{cL}{\pi} \sin(\frac{\pi x}{L})$, then we have a bound

\begin{equation*}
d \geq \varphi(l).
\end{equation*}

Unfortunately, this bound is not strong enough for what we are looking for since

\begin{equation*}
\varphi(x) \approx cx
\end{equation*}

for $x \approx 0$. So, what we need to do is to try and refine the arguments from the Huisken's distance comparison, with the hopes of improving the lower bound on $d$.

To that end, let's introduce a new object.

:::{tip} Definition
:icon: false
Let $X : \mathbb{S}^1 \rightarrow \mathbb{R}^2$ be an embedding. The **chord-arc profile** of $X$ is the function $\psi_X : [0, \infty \rangle \rightarrow \mathbb{R}$ defined by

\begin{equation*}
\psi_X(z) = \inf \left\{ |X(y) - X(x)| : l(x,y) = z \right \}.
\end{equation*}

:::

In some sense, the chord-arc profile allows us to register if a potential singularity might develop by scanning the curve and letting us know what is the smallest chord-distance between any two points on the curve with a given arc-length $z$.

:::{danger} Proposition
:icon: false
Let $X : \mathbb{S}^1 \rightarrow \mathbb{R}^2$ be an embedding and let $C = \sup_{\mathbb{S}^1} |\kappa|$. Then for $z \approx 0$ the following approximation holds:

\begin{equation*}
\psi_X(z) = z - \frac{K^2}{24}z^3 + O(z^5).
\end{equation*}
:::

Given a chord-arc profile of a curve, the result above tells us that we can simply see what's the maximum of the curvature by computing its Taylor expansion around $z_0 = 0$. Also, note that the chord-arc profile could be used to deduce our curvature bounds: suppose that we had a bound of the form $\psi_X \geq z - Cz^3$ for $z \approx 0$. Then for points $x,y$ on our curve with $l \approx 0$ we would have

\begin{equation*}
d \geq \psi_X(l) \geq l - Cl^3,
\end{equation*}

so in the same way as before we could deduce a bound $\kappa^2 \leq 24C$. So, what we now need to do is to obtain lower bounds on the chord-arc profile that are of the form mentioned above.

## Proof of Gage-Hamilton-Grayson's theorem