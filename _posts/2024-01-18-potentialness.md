# On Potentialness
$\newcommand{\norm}[1]{||#1||}$

>[!Index]
>- Potentialness is well-defined
>- We can compute it in a cheaper way
>- Alternative definition?
## Potentialness is well-defined

We decompose $$u = u_p + u_h + u_k$$
And define potentialness $$P(u) = \frac{\norm{u_p}}{\norm{u_p} + \norm{u_h}}$$
Let $u' = u + k$ be a game strategically equivalent to $u$, i.e. $k$ is a non-strategic game. 

$u'$ has the same dynamical and strategical properties of $u$, so we'd like $P(u) = P(u')$ for $P$ to be a good measure. After a short reflection, this is indeed the case, since by definition the potential and harmonic components of $k$ are zero, so $$P(u') = \frac{\norm{u'_p}}{\norm{u'_p} + \norm{u'_h}} = \frac{\norm{u_p}}{\norm{u_p} + \norm{u_h}} $$

## We can compute it in a cheaper way

Recall that Candogan et al. define the deviation map $D: u \mapsto Du$ from a game $u$ to its flow $Du$ (a flow is an assignment of numbers to the edges of the response graph).

For non-strategic games  $Du = 0$; the harmonic and potential components are obtained Hodge-decomposing $Du$, i.e. $Du = Du_p + Du_h$.

I computed potentialness of the flow $Du$ rather than of the payoff $u$ itself:

$$P(Du) = \frac{\norm{Du_p}}{\norm{Du_p} + \norm{Du_h}}$$

This has the advantages of
1. reducing the number of matrices multiplications from $4$ to $2$, and
2. getting rid of the pseudo-inverse altogether (since the pinv is used to go back to $u$ space, but we stay in $Du$ space.)

Compare the code for decomposition in payoff space and in flow space:

```python
    def payoff_decompositon(self):

        u = self.payoff_vector

        PI = self.game.normalization_projection
        e = self.game.exact_projection

        D_pinv = self.game.pwc_matrix_pinv
        D = self.game.pwc_matrix

        uN = u - PI @ u
        uP = D_pinv @ e @ D @ u
        uH = u - uN - uP

        return [uN, uP, uH, phi]
```

```python
    def flow_decomposition(self):

        u = self.payoff_vector

        e = self.game.exact_projection
        D = self.game.pwc_matrix

        Du = D @ u
        DuP = e @ Du.T
        DuH = Du - DuP.T

        return [Du, DuP, DuH]
```

Interestingly, the flow-potentialness turns out to be
- not only invariant under non-strategic transformations (which is expected),
- but also *equal to the payoff-potentialness*:
$$P(u) = P(Du)$$

I don't see an immediate reason why this should be true, but it means we can build on all the results we got so far with this (hopefully) computationally more tractable procedure.

An example for a $2\times2$ game:
```python

# Payoff
u = [1, 7, -3, 0, 1, -2, 5, -6]

# Payoff decomposition
uN = [-1.0, 3.5, -1.0, 3.5, -0.5, -0.5, -0.5, -0.5]

uP = [1.375, 4.125, -1.375, -4.125, 2.125, -2.125, 4.875, -4.875]

uH = [0.625, -0.625, -0.625, 0.625, -0.625, 0.625, 0.625, -0.625]

# Flow
Du = [-3.0, -4.0, -7.0, -11.0]

# Flow decomposition
DuP = [-4.25, -2.75, -8.25, -9.75]

DuH = [1.25, -1.25, 1.25, -1.25]

Payoff potentialness = 0.8460461415885743
Flow potentialness = 0.8460461415885742
```
## Alternative definition?
Food for thoughts; now we have
 $$P(u) = \frac{\norm{u_p}}{\norm{u_p} + \norm{u_h}} = \frac{\norm{Du_p}}{\norm{Du_p} + \norm{Du_h}} $$


We could as well define potentialness as

$$\tilde{P}(u) = \frac{\norm{u_p}}{\norm{u_p + u_h}} = \frac{\norm{Du_p}}{\norm{Du_p + Du_h}} $$

Again working with the payoff or with the flow gives the same result, and by triangle inequality

$$\tilde{P}(u) \geq P(u)$$

So probably we would get qualitatively similar results with a global increase of potentialness; in the previous example this different definition of potentialness gives
```python
Payoff potentialness = Flow potentialness = 0.9838438483563935
```



