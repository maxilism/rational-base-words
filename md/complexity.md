# Factor complexity of minimal words in rational bases

maxilism

24 November 2026

Starting from 1 and rounding $3x/2$ up at each step gives $1,2,3,5,8,12,\ldots$, so the record of which steps require rounding begins $101100\ldots$. More generally, the rounding digits below form the minimal continuation from the node $x_0$ in the representation tree for base $p/q$. [Andrieu, Eliahou and Vivion, Lemma 3.1 and Remark 3.3](https://arxiv.org/html/2510.11723v2#S3.SS1)

**Theorem.** Let $p>q\ge2$ be coprime integers and $x_0$ a positive integer. Set $x_{i+1}=\lceil p x_i/q\rceil$ and $w_i=q x_{i+1}-p x_i$. If $P(n)$ counts the distinct factors of length $n$ of $w$, then

$$\lim_{n\to\infty}\frac{P(n)}n=\infty.$$

Dubickas proved $\liminf P(n)/n\ge \log q/\log(p/q)$ and conjectured $P(n)=q^n$. In base $3/2$, Stephan proved that either $P(n)/n$ is unbounded or the growth constant $\lim_{i\to\infty}(2/3)^i x_i$ is irrational. [Dubickas, Theorem 3 and p. 246](https://doi.org/10.1017/S0017089508004655) · [Stephan, Theorem C](https://arxiv.org/abs/2609.19007)

## Periodic pieces

Write $\lambda=p/q$ and $z=q/p$. The digits satisfy $0\le w_i<q$, so the recurrence gives $x_i\asymp\lambda^i$ and $x_{i+k}\ge\lambda^kx_i$. If the same $k$ digits occur at $i<j$, iteration gives $q^k\mid x_j-x_i$. The sizes increase strictly, so a segment of length $L$ and period $b\le L$ starting at $i$ satisfies

$$q^{L-b}\le x_{i+b}-x_i=O(\lambda^{i+b}).\tag{1}$$

In particular $w$ has no periodic tail.

Suppose $P(n)\le Cn$ for arbitrarily large $n$. Averaging the first differences of $P$ over $\lfloor n/2\rfloor\le h<n$ gives an $h$ with $P(h+1)-P(h)=O(1)$ and $P(h)=O(h)$. Form the Rauzy graph on factors of length $h$, with each factor of length $h+1$ giving an edge from its prefix to its suffix, labelled by its last letter. Mark the initial vertex and every vertex whose indegree or outdegree differs from one. Each vertex has an outgoing edge, only the initial vertex can lack an incoming edge, and the number of edges exceeds the number of vertices by $O(1)$. Thus the number of marks has a fixed bound $R$. The walk spelling $w$ traverses every edge. Contracting the paths between successive marks gives boundedly many edges, labelled by words of length $O(h)$.

Call a contracted edge short if its label has length at most $h/(2R)$. In the graph of short edges, each strongly connected component containing a cycle is a single cycle. Otherwise two edges leaving the same mark inside the component start with different letters. Complete each to a return walk of at most $R$ edges. If $A,B$ are their labels, both $AB$ and $BA$ return to the same factor of length $h$. As $|A|+|B|\le h$, both equal its suffix of that length, contradicting their different first letters.

Between successive long edges the walk visits each short component at most once. In each cycle, group the complete laps as a power of the word read from its entry mark and keep the remaining edges individually. A tail of short edges alone would be periodic. The suffix beginning at $h$ therefore splits into powers of words $W_1,\ldots,W_t$, with $t=O(1)$ and each $|W_j|=O(h)$. The possible words are edge labels and cycle labels read from any of at most $R$ entry marks. Write $u_0=0<u_1<\cdots$ for the piece boundaries relative to $h$. Only boundedly many pieces separate successive long edges, each of length greater than $h/(2R)$. For fixed $N$, applying (1) successively to the first $N$ pieces bounds their total length. Hence, for constants $c>0$ and $c'$ independent of $N$ and $h$,

$$cN-c'\le u_N/h,\qquad u_N=O_N(h).\tag{2}$$

## Comparing the real and $\ell$-adic sizes

The periodic repetition of $W=w_0'\cdots w_{b-1}'$ gives the geometric sum

$$A(W)=\frac{\sum_{j<b} w'_j z^j}{p(1-z^b)}.$$

Its denominator divides $p^b-q^b$ and $0\le A(W)\le(q-1)/(p-q)$. Write $A_i$ for the value at the piece starting at $u_i$. Summing the recurrence across that piece gives $x_{h+u_i}+A_i=z^{u_{i+1}-u_i}(x_{h+u_{i+1}}+A_i)$. Multiplying by $z^{u_i}$ and summing over pieces gives

$$E_N=x_h+A_0+\sum_{i=1}^{N-1}z^{u_i}(A_i-A_{i-1})
     =z^{u_N}(x_{h+u_N}+A_{N-1}).\tag{3}$$

Fix a prime $\ell\mid q$ and put $\rho=\ell^{v_\ell(q)}$. The least common denominator $D$ of the $A(W_j)$ is prime to $q$ and at most $\exp(O(h))$. Put $F_N=DE_N$ and $b=D(x_h,A(W_1),\ldots,A(W_t))$. By (3),

$$F_N\ge Dx_h,\qquad |F_N|_\ell\le\rho^{-u_N}.$$

Thus each $b_a$ is a nonnegative integer of size at most $\exp(O(h))$ and satisfies $b_a=O(F_N)$ uniformly in $N$. Translating (3) by powers of $z$ makes a fixed proportion of the linear forms in the Subspace Theorem small at $\ell$.

Fix $N$ and pass to a subsequence in $h$ on which $t$ and the labels of the first $N$ pieces are fixed. Choose $K$ with $2^K>(K+1)^N$. Among all sums of at most $K$ of the exponent sequences $u_0,\ldots,u_{N-1}$, pass to a subsequence on which every pairwise difference is constant or tends to $\pm\infty$. Identify sequences differing by a constant and order their classes by eventual size. Let $J$ consist of the original $N$ exponent classes and write $mJ$ for their $m$-fold sumset, with $0J=\lbrace 0\rbrace$. Since $|KJ|\le(K+1)^N<2^K$, some $B=mJ$ with $m<K$ satisfies $|B+J|\le2|B|$.

Represent each class by a sum with the fewest summands. Changing representatives only multiplies $z^v$ by a fixed rational. Consider the coordinates $b_a z^v$, $v\in B+J$, as sequences modulo eventual equality. Restrict to an infinite subsequence minimizing the dimension of their rational span and choose a tuple $X$ of coordinates forming a basis. By minimality these $d\le(t+1)|B+J|$ sequences remain independent on every infinite subsequence.

List $B=\lbrace g_1<\cdots<g_s\rbrace$. By (3) there is a fixed rational matrix $M$ such that

$$MX=F_N(z^{g_1},\ldots,z^{g_s})^{\mathsf T}.$$

The first $j$ rows have rank $j$ on the columns with exponent $v\le g_j$. Indeed, any nonzero rational combination of these rows gives $F_N\sum_{i\le j}c_i z^{g_i}$, whose absolute value is eventually at least a fixed positive multiple of $F_N z^{g_j}$ since its least exponent dominates. Each column with $v>g_j$ is $o(F_N z^{g_j})$. Scanning columns in increasing exponent order and keeping each increase in rank therefore gives an invertible $s$-column minor with exponents $v_j\le g_j$.

Use the coordinate forms at all places in $S=\lbrace\infty\rbrace\cup\lbrace r:r\text{ prime},\ r\mid pq\rbrace$. At $\ell$ replace the selected $s$ coordinates by the rows of $M$. The minor ensures independence. Each original coordinate contributes at most $\exp(O(h))$ to the product over $S$, since $z$ is an $S$-unit. The basis coordinates are eventually nonzero, and $|b_a|_\ell^{-1}\le b_a$ for a nonzero entry. Replacing the coordinate $b_a z^{v_j}$ by $F_N z^{g_j}$ therefore multiplies the product by at most $\exp(O(h))\rho^{-u_N+v_j-g_j}$. As $v_j\le g_j$ eventually and $d\le2(t+1)s$, the product of all forms satisfies

$$\log\prod_{v\in S}\prod_{i=1}^d |L_{v,i}(X)|_v\le s(Hh-u_N\log\rho),$$

with $H$ independent of $N$ and $B$.

Choose $N$ large enough in (2) that this bound is at most $-h$. A common $S$-unit clears all denominators of $X$ without changing the product. For fixed $N,B$, (2) bounds the sup norm of the resulting integer vector by $\exp(O_{N,B}(h))$. The product is therefore at most $\lVert X\rVert_\infty^{-\varepsilon}$ for some $\varepsilon>0$ after scaling. In dimension one the product formula already gives a positive lower bound for this product on nonzero integers. In higher dimension Schlickewei’s $S$-adic Subspace Theorem gives a fixed nonzero rational relation on an infinite subsequence, contradicting the choice of $X$. [Evertse, Theorem 4, equation (17)](https://www.numdam.org/item/CM_1984__53_2_225_0.pdf#page=8)

© 2026 maxilism. Licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
