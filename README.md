# Davide Legacci - Research


## 🏠 [Home](https://davidelegacci.it/)

## List
<ul>
  {% for post in site.posts %}
    <li>
      <a href=".{{ post.url }}">{{ post.title }}</a>
      {{ post.excerpt }}
    </li>
  {% endfor %}
</ul>

## WIP

  {% for post in site.posts %}
  
  <a href=".{{ post.url }}">{{ post.title }}</a>
  {{ post.excerpt }}

  {% endfor %}


## Manual

Foo
## Hamiltonian Riemannian Game Dynamics
Riemannian game dynamics are dynamics for one-population games induced by the payoff vector field. Under some circumstances, such dynamics display Hamiltonian properties.

➡️ [Hamiltonian Riemannian Game Dynamics](./_posts/2024-01-17-hamiltonian-riemannian-dynamics.md)

## Geometric Aspects of Learning and Evolution in Games
The space of finite normal form games admits a non-canonical direct sum decomposition into the subspaces of non-strategic, potenti, and harmonic games, closely related to the discrete Hodhe decomposition for simplicial complexes. I am interested in an analogue decomposition for games with continuous strategy space (concave games), and continuous population space (population games).