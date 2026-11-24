# Rational-base words

Starting from a positive integer $x_0$, repeatedly multiply by a fixed reduced fraction $p/q$ with $p>q>1$ and round up to get $x_{i+1}=\lceil p x_i/q\rceil$. The digit $w_i=q x_{i+1}-p x_i$ records the rounding at step $i$, so in base $3/2$ it is 1 when rounding is needed and 0 otherwise.

* **Factor complexity of minimal words in rational bases.** If $P(n)$ counts the distinct blocks of $n$ digits, then $P(n)/n\to\infty$. Dubickas conjectured that all $q^n$ blocks occur. [Paper](complexity.pdf) · [Source](md/complexity.md) · [Dubickas, p. 246](https://doi.org/10.1017/S0017089508004655)
* **Nonautomaticity of minimal words in rational bases.** No finite automaton reading the index $i$ in an integer base $k\ge2$ can output $w_i$ for every $i$. Automatic words have at most linearly many factors of length $n$, so the complexity theorem implies this conclusion. The one-page paper gives an independent proof using Mahler’s method. [Paper](nonautomaticity.pdf) · [Source](md/nonautomaticity.md)

© 2026 maxilism. Both papers and their sources are licensed under [CC BY 4.0](LICENSE).
