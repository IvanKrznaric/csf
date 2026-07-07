# Long Time Behaviour

:::{prf:theorem} @MR840401, @MR906392
:label: gage-hamilton-grayson

The CSF exists on the maximal time interval $[0, T)$ where $T = \tfrac{A_0}{2\pi}$ where $A_0$ is the initial area. Upon rescaling to fix the total length, the CSF converges smoothly to a circle of total length $L_0$ as $t \to T$ where $L_0$ is the initial length.
:::

A useful place to find information about the theorem is the [Wikipedia article on CSF](https://en.wikipedia.org/wiki/Curve-shortening_flow#Gage%E2%80%93Hamilton%E2%80%93Grayson_theorem)

# Intuition, motivation

# Huisken's distance comparison

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
Let $X : [0, T \rangle \times \mathbb{S}^1 \rightarrow \mathbb{R}^2$ be a solution of the curve shortening flow such that $X(0, \cdot)$ is an embedding. Then $\sup \left\{ Z(t,x,y) : x,y \in \mathbb{S}^1 \right \}$ is non-increasing in time.
:::

# Curvature bounds via distance comparison

# Proof of Gage-Hamilton-Grayson's theorem