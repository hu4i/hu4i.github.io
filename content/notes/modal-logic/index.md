---
title: "Modal Logic"
date: 2023-06-18T08:41:11+08:00
draft: true
---

These are notes taken from the book of Blackburn et al. {{< cite Blackburn2001 >}}

## 1 Basic Concepts

### 1.1 Relational Strucures

{{< admonition type=note title="Definition 1.1 (Relational Structure)" open=true >}}

> Keywords: relational structure $\mathfrak{F}$, universe (or domain) $W$, relation on the universe $R$.

{{< /admonition >}}

{{< admonition type=example title="Example 1.2-1.5 (Relational Structures)" open=true >}}

> Keywords:
>
> - Example 1.2 (Orders)
>   - Strict partial order (SPO).
>   - Linear order (or total order).
>   - Partial order.
>   - Reflexive linear order (or reflexive total order).
>   - Irreflexive, transitive, trichotomy condition, reflexive, antisymmetric.
> - Example 1.3 (Labeled Transition Systems, LTSs)
>   - Deterministic
>   - Non-deterministic
> - Example 1.4 (Knowledge representation)
> - Example 1.5 (Finite trees)

{{< /admonition >}}

{{< admonition type=note title="Definition 1.6" open=true >}}

> Keywords: transitive closure $R^+$, reflexive transitive closure $R^+$.

{{< /admonition >}}

{{< admonition type=note title="Definition 1.7 (Tree)" open=true >}}

> Keywords: tree $\mathfrak{T}$, root, acyclic, tree-like, (reflexive and) transitive trees.

{{< /admonition >}}

{{< admonition type=example title="Example 1.8 (Arrow Structure)" open=true >}}

> Keywords:
>
> - Arrow Structures
> - Two-dimensional arrow structure
> - Arrow frame
>   - Composition relation
>   - Reverse relation
>   - Identity arrows (predicate?)
> - Square over $U$, notation: $\mathfrak{S}_U$

{{< /admonition >}}

### 1.2 Modal Languages

{{< admonition type=note title="Definition 1.9 (Basic Modal Language)" open=true >}}

> Keywords: basic modal language, set of proposition letters $\Phi$, modal operator $\diamond$ (diamond), modal operator $\square$ (box), well-formed formulas $\phi$

{{< /admonition >}}

{{< admonition type=example title="Example 1.10 (Three Important Readings of diamond and box)" open=true >}}

> Keywords: necessarily $\phi$, knows $\phi$, is provable that $\phi$.

{{< /admonition >}}

{{< admonition type=note title="Definition 1.11 Modal Similarity Type" open=true >}}

> Keywords: modal similarity type $\tau = (O, \rho)$, modal operators $O$, operators $\delta \in O$ function $\rho$: $O \rightarrow \mathbb{N}$ that assigns operator in $O$ a finite arity.
> Notes: sometimes $\tau$ and $O$ is not distinguished assuming that the arity of operators is known.

{{< /admonition >}}

{{< admonition type=note title="Definition 1.12" open=true >}}

> Keywords: modal language $\textit{ML}(\tau, \Phi)$, set $\textit{Form}(\tau, \Phi)$ of modal formulas, nullary modalities (modal constants).

{{< /admonition >}}

{{< admonition type=note title="Definition 1.13 (Dual Definitions for Non-nullary triangles)" open=true >}}

> Keywords: nabla $\nabla$, box.

{{< /admonition >}}

{{< admonition type=example title="Example 1.14-1.17" open=true >}}

- The basic temporal language
- 

TBD

{{< /admonition >}}

{{< admonition type=note title="Definition 1.18 (Substitution)" open=true >}}

TBD

{{< /admonition >}}

### 1.3 Models and Frames

## Bibliography

Blackburn2001 {{< label Blackburn2001 bib >}}
: Blackburn, P., Rijke, M. de, & Venema, Y. (2001). Modal logic. Cambridge University Press. https://doi.org/10.1017/CBO9781107050884
