# Nonautomaticity of minimal words in rational bases

maxilism

24 November 2026

For coprime integers $p>q>1$, start at a positive integer $x_0$ and define the ceiling orbit and its digits by

$$
x_{n+1}=\left\lceil\frac{p x_n}{q}\right\rceil,\qquad
w_n=q x_{n+1}-p x_n\in\lbrace 0,\ldots,q-1\rbrace.
$$

The word $w=w_0w_1\cdots$ is the minimal continuation from node $x_0$ in base $p/q$. In base $3/2$ its digits record the parity of $x_n$, and Stephan proved that $w$ is nonautomatic if the growth constant $\lim_{n\to\infty}(2/3)^n x_n$ is algebraic. [Andrieu, Eliahou and Vivion, Lemma 3.1 and Remark 3.3](https://arxiv.org/html/2510.11723v2#S3.SS1) · [Stephan, Theorem B](https://arxiv.org/html/2609.19007v2#S1)

**Theorem.** The word $w$ is not $k$-automatic for any integer $k\ge2$.

**Proof.** Write $X(z)=\sum_{n\ge0}x_nz^n$ and $W(z)=\sum_{n\ge0}w_nz^n$. The recurrence gives

$$
X(z)=\frac{q x_0+zW(z)}{q-pz}.
$$

The bounded, nonnegative digits make the numerator analytic on $|z|<1$ and positive at $\alpha=q/p$. Thus $X$ is analytic on $|z|<\alpha$ and has a simple pole at $\alpha$.

Suppose $w$ is $k$-automatic. Then $W$ is $k$-Mahler, and the displayed identity makes $X$ $k$-Mahler as well, since its iterates $X(z^{k^j})$ lie in the finite-dimensional $\mathbb Q(z)$-span of $1$ and the iterates $W(z^{k^j})$. [Adamczewski, Bell and Smertnig, §§3.1–3.3](https://ems.press/content/serial-article-files/32888#page=8)

The $k$-Mahler denominator $d$ of $X$ then satisfies

$$
d(z)X(z)=\sum_{j=1}^{m}a_j(z)X(z^{k^j}),\qquad a_j\in\mathbb Q[z].
$$

Since $\alpha^{k^j}<\alpha$ for $j\ge1$, the right side is analytic at $\alpha$. The pole of $X$ therefore forces $d(\alpha)=0$. [Adamczewski, Bell and Smertnig, Definition 3.9](https://ems.press/content/serial-article-files/32888#page=11)

Choose a prime $\ell\mid q$. Coprimality gives $0<\lvert\alpha\rvert_{\ell}<1$. Proposition 6.4 of Adamczewski, Bell and Smertnig now gives $X$ an $\ell$-adic radius of convergence strictly less than one. Yet $\lvert x_n\rvert_{\ell}\le1$ for every $n$, so the radius is at least one. $\square$ [Proposition 6.4](https://ems.press/content/serial-article-files/32888#page=18)

In the representation tree of expansions without leading zeros, the theorem also covers the minimal word at the root, since it begins with the digit $q$ and then follows the minimal word from node $1$. To obtain the maximal word at any node $s\ge0$, add $p-q$ to each digit of the minimal word at $s+1$. Shifting the index and relabelling the digits bijectively preserve automaticity, so every maximal word is also nonautomatic in every integer base $k\ge2$. [Andrieu, Eliahou and Vivion, §2.4](https://arxiv.org/html/2510.11723v2#S2.SS4)

© 2026 maxilism. Licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
