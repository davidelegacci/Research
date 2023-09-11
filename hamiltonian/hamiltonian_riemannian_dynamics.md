---
usemathjax: true
---
# Hamiltonian Riemannian Game Dynamics

## Changes checker


#hamiltonian-game-dynamics #evolutionary-game-theory #replicator-dynamics

## Evolutionary game dynamics
Evolutionary game dynamics is a well-established interdisciplinary subject with far-reaching applications to genetics, ecology, chemistry, physics of complex systems, sociobiology and economics[^hof][^san].

Broadly speaking it models the evolution of a population of individuals divided into sub-populations mutually interacting with each other, the interaction being effectively captured by so-called *fitness functions*.

The fraction of the individuals belonging to a subpopulation $i$ is given by a number $x_i$ between $0$ and $1$, so that the state $x$ of the entire population at any given time is described by a point on the standard simplex $\Delta$. The fitness of a subpopulation when the population is at some state is then a real number $f_i(x)$ depending on the subpopulation and the population state, and the fraction of individuals belonging to a given subpopulation expands or shrink over time according to a dynamical system on the simplex

$$\dot{x} = X(x) \tag{1} $$

the vector field $X$ being generated in some way by the fitness functions $f$.


## Riemannian game dynamics
Mertikopoulos and Sandholm[^mer-san] showed that one way of generating the dynamical system $(1)$ in the interior of the simplex from the fitness functions $f$ is by means of a Riemannian metric $g$, demanding the motion to minimize the difference between a _cost_ function and a _gain_ function:
$$X(x) = \text{argmin}_{v \in T_x{\Delta}} \left( \frac{1}{2} ||v||_x^2 - v \cdot f(x) \right) \tag{RGD-1}$$
This is equivalent to orthogonally projecting (with respect to $g$) the vector field $f^{\sharp}$ on the simplex, where $\sharp$ is the [sharp isomorphism](https://en.wikipedia.org/wiki/Musical_isomorphism) associated with the metric $g$ and $f$ is seen as a $1$-form. The vector field $(\text{RGD-1})$ is then equivalent to

$$X = f^{\sharp} - \frac{f^{\sharp} \cdot \mathbb{1}}{n \cdot \mathbb{1}}n \tag{RGD-2}$$

where $\mathbb{1} = (1, \dots, 1)$, and $n = \mathbb{1}^{\sharp}$ is a vector field normal to the simplex.

## Shahshahani metric and zero-sum replicator dynamics
If $g$ is the Shahshahani metric[^sha][^akin90]
$$g(x) = \sum_{i,j} \frac{\delta_{ij}}{x_i}  dx^i \otimes dx^j$$
then $(\text{RGD-2})$ becomes the *replicator field*[^shu]
$$X^i(x) = x^i \left( f_i(x) - \sum_j x^j f_j(x) \right)$$
which says that the growth rate of a sub-population is equal to the difference between its fitness and the average fitness of the population.

The explicit expression of the fitness depends on the system under consideration. In this work we investigate the case in which the fitness depends **linearly** on the population state
$$f(x) = Ax$$
and the game is **zero-sum,** namely the fitness matrix $A$ is anti-symmetric.
## Zero-sum Hamiltonian replicator systems
A breakthrough paper by Akin and Losert[^Akin84] showed that anti-symmetric zero-sum replicator systems yield a symplectic foliation on the standard simplex and the following dichotomy holds: Either

-   the replicator system has interior fixed points and the system is Hamiltonian, with Hamiltonian function given by the *Kullback-Leibler divergence*[^baez],
-   or there are two subsimplices contained in the boundary of the main simplex such that all solutions of the replicator system are backward-asymptotic to one subsimplex, forward-asymptotic to the other and the limit dynamics on both subsimplices is Hamiltonian.

Focusing on the first case, Alishah and Duarte[^ali15] showed that the symplectic foliation of the simplex arises from a stratified Poisson structure[^ort] on the simplex, in which the replicator system is Hamiltonian. This result was recently generalised in the context of Dirac / Big-isotropic structures[^ali20].

### Master thesis outline
In [my master thesis](https://www.mathi.uni-heidelberg.de/~geodyn/teaching/Theses/MA_Davide_Legacci.pdf) (May 2020) I investigated the Hamiltonian nature of zero-sum replicator systems in presence of interior fixed points with respect to the cubic Poisson structure on the standard simplex described by Alishah and Duarte.

To this end some familiarity with Poisson manifolds is required, with particular focus on the methods of singular Poisson reduction, used to derive the stratified Poisson structure for the standard simplex. After a brief detour into classical concepts of Evolutionary Games and Population Dynamics, I proved the main result, namely the Hamiltonian character of the replicator vector field with respect to the derived Poisson structure, and discussed some simple examples.

## Open research directions
In collaboration with [Prof. Gabriele Benedetti](https://research.vu.nl/en/persons/gabriele-benedetti) I am working along the following directions:

Upon some homogeneity assumptions, the replicator field in the interior of the simplex $\mathring{\Delta}$ can be obtained from the field $x_i f_i(x)$ in $\mathbb{R}^n_{>0}$ via the Poisson quotient map $x \mapsto x / \left(\sum_i x_i \right)$ onto $\mathring{\Delta}$. We study the Hamiltonian structure of this system in $\mathbb{R}^n_{>0}$ with respect to a suitable Poisson structure, and motivate the appearance of the Kullback-Leibler divergence as Hamiltonian function from the fact that it is a Casimir function of such Poisson structure. Starting from an idea by Alishah and Duarte[^ali15] we furthermore developed an algorithm to generate a Hamiltonian zero-sum replicator system with any chosen fixed point.

Next, starting from an idea by Mertikopoulos and Sandholm[^mer-san] on [Bregman divergences](https://en.wikipedia.org/wiki/Bregman_divergence), we are investigating whether such Hamiltonian description generalizes beyond the replicator case to arbitrary conservative Riemannian game dynamics, the answer appearing to be affirmative.

Finally, we want to find periodic orbits of zero-sum replicator systems with interior fixed points by variational methods based on Clarke's duality, exploiting the convexity of the Hamiltonian function[^eke]. In low dimension one can exploit the convexity further to show the existence of a global surface of section for the flow using the work of Hofer, Wysocki and Zehnder[^hofer]. In particular we want to

1.  Determine explicit periodic orbits of given period or energy by numerically minimizing the dual action functional;
2.  Prove the existence of a convex, coercive Hamiltonian on every symplectic leaf when the interior point is not unique.
3.  Adapt the techniques from[^savarino] to numerically determine a global surface of section in dimension four.
4.  Effectively visualize the dynamics of the replicator system, its periodic orbits and the return map associated to the surface of section.
5.  The simplex parametrizes the space of probability densities on the finite set {1, . . . , n}. Formulate an infinite-dimensional version of the replicator equation and of evolutionary zero-sum games for probability densities on Euclidean space[^eochssler].
## Relevant literature
Here is an extremely non-exhaustive list of relevant works beyond the ones explicitly cited so far.

### Evolutionary game dynamics

-   Jörgen W Weibull. _Evolutionary game theory_. MIT press, 1997
-   James Franklin Crow, Motoo Kimura, et al. “An introduction to population genetics theory”. In: _An introduction to population genetics theory_ (1970)
-   Marc Harper. “Information geometry and evolutionary game theory”. In: _arXiv preprint arXiv:**0911**.**1383_ (2009)
-   Josef Hofbauer. “On the occurrence of limit cycles in the Volterra-Lotka equation”. In: _Nonlinear Analysis: Theory, Methods & Applications_ 5.9 (1981), pp. 1003–1007
-   Peter D Taylor and Leo B Jonker. “Evolutionary stable strategies and game dynamics”. In: _Mathematical biosciences_ 40.1-2 (1978), pp. 145–156
-   N. Watanabe, Y. Togawa, and K. Sawada. Hamiltonians which are induced from anti-symmetric replicator equations. Nonlinear Analysis: Theory, Methods and Applications, 36(5):655–660, 1999.

### Smooth manifolds

-   John M. Lee. Introduction to Smooth Manifolds. 2nd ed. Graduate Texts in Mathematics. Springer-Verlag New York, 2012.

### Symplectic and Poisson geometry

-   Ana Cannas da Silva. Lectures on Symplectic Geometry. 1., st ed. 2001. Corr., 2nd printing. Lecture Notes in Mathematics. Springer, 2009.
-   Paulette Libermann and Charles-Michel Marle. Symplectic Geometry and Analytical Mechanics. 1st ed. Mathematics and Its Applications 35. Springer Netherlands, 1987.
-   Izu Vaisman. Lectures on the Geometry of Poisson Manifolds. 1st ed. Progress in Mathematics 118. Birkhäuser Basel, 1994.
-   Jean-Paul Dufour and Nguyen Tien Zung. Poisson Structures and Their Normal Forms. 1st ed. Progress in Mathematics 242. Birkhäuser Basel, 2005.

### Stratified spaces

-   Juan-Pablo Ortega and Tudor S. Ratiu. Momentum Maps and Hamiltonian Reduction. 1st ed. Progress in Mathematics 222. Birkhäuser Basel, 2004.
-   Juan-Pablo Ortega, Tudor S. Ratiu, and Rui Loja Fernandes. “The momentum map in Poisson geometry”. In: American journal of mathematics 131.5 (2009), pp. 1261–1310.
---
_This research was funded by the Deutsche Forschungsgemeinschaft (DFG, German Research Foundation) under Germany ́s Excellence Strategy EXC 2181/1 - 390900948 (the [Heidelberg STRUCTURES Excellence Cluster](https://www.structures.uni-heidelberg.de/))._

[^hof]: J. Hofbauer and K. Sigmund, Evolutionary games and population dynamics, Cambridge University Press, Cambridge, 1998.
[^san]: W. H. Sandholm. Population games and evolutionary dynamics. MIT press, 2010.
[^mer-san]: P. Mertikopoulos and W. H. Sandholm. Riemannian game dynamics. Journal of Economic Theory, 177:315–364, 2018
[^sha]: S. Shahshahani. A new mathematical framework for the study of linkage and selection. American Math- ematical Soc., 1979
[^akin90]: E. Akin, The differential geometry of population genetics and evolutionary games. In Mathematical and Statistical Developments of Evolutionary Theory, pp. 1-93. Springer, Dordrecht, 1990.
[^shu]: P. Schuster and K. Sigmund. Replicator dynamics. Journal of theoretical biology, 100(3):533–538, 1983
[^akin84]: E. Akin and V. Losert, Evolutionary dynamics of zero-sum games, J. Math. Biol. 20 (1984), no. 3, 231-258
[^baez]: John C Baez and Blake S Pollard. “Relative entropy in biological systems”. In: _Entropy_ 18.2 (2016), p. 46
[^ali15]: H. N. Alishah and P. Duarte, Hamiltonian evolutionary games, J. Dyn. Games 2 (2015), no. 1, 33-49
[^ort]: Juan-Pablo Ortega, Tudor S. Ratiu, and Rui Loja Fernandes. "The momentum map in Poisson geometry";. In: American journal of mathematics 131.5 (2009), pp. 1261-1310
[^ali20]: H. N. Alishah. Hamiltonian formalism of the inverse problem using dirac geometry and its application on linear systems, 2020
[^eke]: Ekeland, I. (2012). Convexity methods in Hamiltonian mechanics (Vol. 19). Springer Science & Business Media.
[^hofer]: Hofer, H., Wysocki, K., & Zehnder, E. (1998). The Dynamics on Three-Dimensional Strictly Convex Energy Surfaces. Annals of Mathematics, 148(1), second series, 197-289. doi:10.2307/120994
[^savarino]: F. Savarino and C. Schnörr, Continuous-Domain Assignment Flows, preprint available at arXiv:1910.07287, 2019.
[^eochssler]: Oechssler, J. and Riedel, F. (2001). Evolutionary dynamics on infinite strategy spaces. Economic theory, 17(1):141–162