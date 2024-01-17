# Davide Legacci - Research

---

<ul> {% for post in site.posts %} <li> <a href="Research{{ post.url }}">{{ post.title }}</a> </li> {% endfor %} </ul>

<ul> {% for post in site.posts %} <li> <a href="{{ post.url }}">{{ post.title }}</a> </li> {% endfor %} </ul>

---

## 🏠 [Back to main site](https://davidelegacci.it/)

## Hamiltonian Riemannian Game Dynamics
Riemannian game dynamics[^mert] are dynamics for one-population games induced by the payoff vector field. Under some circumstances, such dynamics display Hamiltonian properties[^ali].

➡️ [Hamiltonian Riemannian Game Dynamics](./hamiltonian/hamiltonian_riemannian_dynamics.md)

## Geometric Aspects of Learning and Evolution in Games
The space of finite normal form games admits a non-canonical direct sum decomposition into the subspaces of non-strategic, potenti, and harmonic games[^can], closely related to the discrete Hodhe decomposition for simplicial complexes. I am interested in an analogue decomposition for games with continuous strategy space (concave games), and continuous population space (population games)

➡️ [Geometric Aspects of Learning and Evolution in Games](./learning/geometry_learning.md)

[^ali]: Alishah HN, Duarte P (2014) Hamiltonian evolutionary games. _arXiv preprint arXiv:1404.5900_.
[^mert]: Mertikopoulos P, Sandholm WH (2018) Riemannian game dynamics. _Journal of Economic Theory_ 177:315–364.
[^can]: Candogan O, Menache I, Ozdaglar A, Parrilo PA (2011) Flows and Decompositions of Games: Harmonic and Potential Games. _Mathematics of Operations Research_ 36(3):474–503.