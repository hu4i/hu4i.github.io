---
title: "Modal Logic"
date: 2023-06-18T08:41:11+08:00
mermaid: true
---

Languages of modal logic are useful tools for describing and reasoning about relational structures which are widely spread in many subjects. These are notes taken from *Modal Logic*, the book of Blackburn et al. {{< cite Blackburn2001 >}}

## 1 Basic Concepts

{{< mermaid >}}
flowchart TD
  RS[Relational Structure, Def. 1.1]
  ML[Modal Language, Def. 1.12]
  FM[Frame and Model, Def. 1.19]
  SAT[Satisfaction, Def. 1.20]
  VA[Validity, Def. 1.28]
  RS & ML --> FM --> SAT --> VA
{{< /mermaid >}}

### 1.1 Relational Structures

{{< admonition type=note title="Definition 1.1 (Relational Structure)" open=true >}}

> Relational structure $\mathfrak{F}$; Universe (or domain) $W$; Relation**s** on the universe $R$.

{{< /admonition >}}

{{< admonition type=example title="Example 1.2-1.5 (Relational Structures)" open=true >}}

> - Example 1.2 (Orders)
>   - Strict partial order (SPO); Linear order (or total order); Partial order; Reflexive linear order (or reflexive total order); Irreflexive; Transitive; Trichotomy condition; Reflexive; Antisymmetric.
> - Example 1.3 (Labeled Transition Systems, LTSs)
>   - Deterministic; Non-deterministic.
> - Example 1.4 (Knowledge representation)
> - Example 1.5 (Finite trees)

{{< /admonition >}}

{{< admonition type=note title="Definition 1.6 (Transitive Closure)" open=true >}}

> Transitive closure $R^+$; Reflexive transitive closure $R^+$.

{{< /admonition >}}

{{< admonition type=note title="Definition 1.7 (Tree)" open=true >}}

> Tree $\mathfrak{T}$; Root; Acyclic; Tree-like; (Reflexive and) Transitive trees.

{{< /admonition >}}

{{< admonition type=example title="Example 1.8 (Arrow Structure)" open=true >}}

> - Arrow Structures; Two-dimensional arrow structure;
> - Arrow frame; Composition relation; Reverse relation; Identity arrows (predicate?);
> - Square over $U$, notation: $\mathfrak{S}_U$.

{{< /admonition >}}

### 1.2 Modal Languages

{{< admonition type=note title="Definition 1.9 (Basic Modal Language)" open=true >}}

> Basic modal language; Set of proposition letters $\Phi$; Modal operator $\diamond$ (diamond); Well-formed formulas $\phi$.

{{< /admonition >}}

{{< admonition type=example title="Example 1.10 (Three Important Readings of Diamond and Box)" open=true >}}

> $\square \phi$: necessarily $\phi$; knows $\phi$; is provable that $\phi$.

{{< /admonition >}}

{{< admonition type=note title="Definition 1.11 (Modal Similarity Type)" open=true >}}

> Modal similarity type $\tau = (O, \rho)$; Modal operators $O$; Operators $\triangle \in O$; Function $\rho$: $O \rightarrow \mathbb{N}$ that assigns operator in $O$ a finite arity; Define unary triangles as diamonds, denoted as $\Diamond_a$ or $\langle a \rangle$, where $a$ is taken from some index set.

Notes: sometimes $\tau$ and $O$ is not distinguished assuming that the arity of operators is known.

{{< /admonition >}}

{{< admonition type=note title="Definition 1.12 (Modal Language)" open=true >}}

> Modal language $\rm{ML}(\tau, \Phi)$; Set $\rm{Form}(\tau, \Phi)$ of modal formulas; Nullary modalities (modal constants); The similarity type of the basic modal language is called $\tau_0$; For binary modal operators, use $\phi \triangle \psi$ instead of $\triangle(\phi, \psi)$; Nullary modalities (or modal constants).

{{< /admonition >}}

{{< admonition type=note title="Definition 1.13 (Dual Definitions for Non-nullary Triangles)" open=true >}}

> Dual of $\triangle$, written as nabla $\nabla$; Dual of $\Diamond_a$, written as box $\square_a$ or $[a]$.

{{< /admonition >}}

{{< admonition type=example title="Example 1.14-1.17" open=true >}}

> Keywords
>
> - Example 1.14 (Basic Temporal Language)
>   - $O = \\{ \langle F \rangle, \langle P \rangle \\}$; Intended interpretation of $\langle F \rangle (\phi)$ is '$\phi$ will be true at some future time', $\langle P \rangle (\phi)$ is '$\phi$ was true at some past time', traditionally write as $F$ and $P$ respectively; $G$ and $H$ are their duals respectively, means 'going to be' and 'always has been'.
> - Example 1.15 (Propositional Dynamic Logic)
>   - Modal operators are denoted as $\langle \pi \rangle$, where $\pi$ denotes a (nondeterministic) program; Intended interpretation of $\langle \pi \rangle (\phi)$ is 'some terminating execution of $\pi$ from the present state leads to a state bearing the information $\phi$'; Complex programs are defined inductively on some basic programs.
> - Example 1.16 (An Arrow Language)
>   - Arrow logic; Identity; Converse; Composition.
> - Example 1.17 (Feature Logic and Description Logic)
>   - Attribute-Value Matrices (AVMs); Feature structures;

{{< /admonition >}}

{{< admonition type=note title="Definition 1.18 (Substitution)" open=true >}}

> Substitution $\sigma: \Phi \rightarrow \rm{Form}(\tau, \Phi)$; Map $(\cdot)^\sigma: \rm{Form}(\tau, \Phi) \rightarrow \rm{Form}(\tau, \Phi)$ induced by $\sigma$; Substitution instance.

{{< /admonition >}}

### 1.3 Models and Frames

{{< admonition type=note title="Definition 1.19 (Frame and Model)" open=true >}}

> Frame $\mathfrak{F} = (W, R)$; Model $\mathfrak{M} = (\mathfrak{F}, V)$; Valuation function $V: \Phi \rightarrow \mathcal{P}(W)$ (it assigns to each proposition letter $p$ in $\Phi$ a subset $V(p)$ of $W$); Model $\mathfrak{M}$ is based on the frame $\mathfrak{F}$, or $\mathfrak{F}$ is the frame underlying $\mathfrak{M}$.

{{< /admonition >}}

The model $(W, R, V)$ for a basic modal language can be viewed as relational structure, where $V$ gives unary relations when given $p \in \Phi$.

Frames and models are used very differently:

- > Frames are essentially mathematical pictures of ontologies that we find interesting.
- > The unary relations provided by valuations, on the other hand, are there to dress our frames with contingent information.

{{< admonition type=note title="Definition 1.20 (Satisfaction)" open=true >}}

> A formula $\phi$ being satisfied (or true) in $\mathfrak{M}$ at state $w$: $\mathfrak{M}, v \models \phi$; Set $\Sigma$ of formulas is true in $\mathfrak{M}$ at state $w$: $\mathfrak{M}, v \models \Sigma$; Extend valuation $V$ from proposition letters to arbitrary formulas $\phi$: $V(\phi) := \\{ w \mid \mathfrak{M}, w \models \phi \\}$.

Note: If context is clear, $\mathfrak{M}$ can be omitted.

{{< /admonition >}}

This notion of satisfaction is internal and local:

- Internal: Formulas are evaluated inside models, at some particular sate $w$ (the current state).
- Local: only successors of the current state can be scanned by modal operators.

{{< admonition type=note title="Definition 1.21 (Satisfiable)" open=true >}}

> Globally or universally true in a model $\mathfrak{M}$; Satisfiable in a model $\mathfrak{M}$; Falsifiable and refutable in a mode.

{{< /admonition >}}

{{< admonition type=example title="Example 1.22" open=true >}}

- Observe that diamond $\Diamond$ corresponds to making a single $R$-step in a model, we write $\Diamond^n \phi$ for $\phi$ proceeded by $n$ occurrences of $\Diamond$, similarly for $\square^n \phi$; $R^0xy$ and $R^{n+1}xy$ are defined similarly;
- > Varying $R$ is a mechanism which gives us a firm mathematical grip on the pre-theoretical notion of access between possible worlds;
- Interpretation of $\square$ in epistemic logic.

{{< /admonition >}}

{{< admonition type=note title="Definition 1.23 ($\tau$-frame)" open=true >}}

> $\tau$-frame; Nullary modalities do not access other states, they are part of the underlying frame.

{{< /admonition >}}

{{< admonition type=example title="Example 1.24-1.27" open=true >}}

> - Example 1.25 (Bidirectional Frames and Models)
>   - $\check{R}$, converse of a relation $R$; Bidirectional frame; Bidirectional model.
> - Example 1.26 (Regular Frames and Models)
>   - $\Pi$, the programs constructed inductively on basic programs and some basic constructors; Regular frame for $\Pi$; Regular model for $\Pi$.
> - Example 1.27 (Arrow Models)

{{< /admonition >}}

{{< admonition type=note title="Definition 1.28 (Validity)" open=true >}}

> $\mathfrak{F}, w \models \phi$: $\phi$ is valid at a state $w$ in a frame $\mathfrak{F}$; $\mathfrak{F} \models \phi$: $\phi$ is valid in a frame $\mathfrak{F}$; $\mathsf{F} \models \phi$: $\phi$ is valid on a class of frames $\mathsf{F}$; $\models \phi$; $\Lambda_\mathsf{F}$: logic of $\mathsf{F}$.

{{< /admonition >}}

{{< admonition type=note title="Example 1.29" open=true >}}

> - Transitive frames;
> - When additional constraints are imposed on frames, more formulas may become valid;

{{< /admonition >}}

## Bibliography

Blackburn2001 {{< label Blackburn2001bib >}}
: Blackburn, P., Rijke, M. de, & Venema, Y. (2001). Modal logic. Cambridge University Press. https://doi.org/10.1017/CBO9781107050884
