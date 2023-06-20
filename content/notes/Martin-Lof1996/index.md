---
title: "On the meanings of the logical constants and the justifications of the logical laws"
date: 2023-06-20T13:33:34+08:00
draft: false
---

These lectures notes {{< cite Martin-Lof1996 >}} are well-known materials of intuitionistic logic and Martin's type theory. But it seems I need more logical and mathematical experiences and knowledge to fully understand these lecture notes.

## First Lecture

### Historical and Modern Interpretation of Propositions and Assertions

Before diving into the main topic about logical constants and logical laws, two entities they operate on (propositions and assertions, respectively) must be discussed and determined.

Martin talked about the source and evolution of some logical concepts in the history, I think the key points are:

- The ambiguity of the word judgment: the act of judging and that which is judged.

- The proposition in **old** sense: the (categorical) proposition can be divided into affirmations and denials.

- What sort of thing is it that is affirmed in an affirmation ($A \text{ is true}$) and denied in a denial ($A \text{ is false}$)? That is, what sort of thing is the $A$ here?. The isolation of this concept (what sort of thing is the $A$) was a step which was entirely necessary for the development of modern logic.

Then he pointed that, through the development of logic, the two entities have their meaning that differs from history usage:

- Assertions (or judgments): the things we prove, in particular, the premises and conclusion of a logical inference, are no longer propositions in Russell's terminology, but assertions (or judgments).
- Propositions: the things that we combine by means of the logical operations, the connectives and the quantifiers, are not propositions in the old sense, that is, what Russell calls assertions, but what he calls propositions.

### Replace Formulae with Propositions

But he hadn't given his attempting at defining the notions of the two entities. To motivate next step, he came up with the rule of disjunction introduction:

$$
\begin{prooftree}
\AXC{$A$ true}
\UIC{$A \lor B$ true}
\end{prooftree}
$$

The question is: What do the variables $A$ and $B$ range over in a rule like this?

- A typical answer that would be that they range over arbitrary formulas of the language that you are considering. But it is strange for its language dependence.

Martin concluded that $A$ and $B$ should range over propositions. Because the notion of formula is nothing but the formalistic substitute for the notion of proposition. But there is another difficult occurs:

> Whereas the notion of formula is a **syntactic** notion, a formula being defined as an expression that can be formed by means of certain formation rules, the notion of proposition is a **semantic** notion, which means that the rule is no longer completely formal in the strict sense of formal logic.

He pointed out:

> That a rule of inference is completely formal means precisely that there must be no semantic conditions involved in the rule: it may only put conditions on the forms of the premises and conclusion.

So the only way out of this difficulty is to give the rule there premises:

$$
\begin{prooftree}
\AXC{$A$ prop}
\AXC{$B$ prop}
\AXC{$A$ true}
\TIC{$A \lor B$ true}
\end{prooftree}
$$

Where $A \text{ prop}$ is an abbreviation of $A \text{ is a proposition}$.

### Adapt the Meaning of Judgement

Now we say variable $A$ and $B$ can range over anything, that is, any expressions. The author didn't want to go into the analysis of expressions because it is comparatively trivial matter, he said:

> An expression in the most general sense of the word is nothing but a form, that is, something that we can passively recognize as the same in its manifold occurrences and actively reproduce in many copies. But I think that I shall have to rely here upon an agreement that we have such a general notion of expression, which is formal in character, so that the rule can now count as a formal rule.

From the conclusion of the first section, we call what we prove (in particular, the premises and conclusion of a logical inference) by the judgment (or assertion), in the modern terminology. Because $A \text{ prop}$ and $B \text{ prop}$ becomes premises of the rule of disjunction introduction, it comes out that

$$
\begin{equation*}
    A \text{ is a proposition}
\end{equation*}
$$

must count as **a form of judgement**.

If $A \text{ prop}$ is a form of judgment, it immediately follows that traditional defintion of the act of judging as an act of affirmation or denial has to be rejected. Because $A \text{ prop}$ is certainly neither an affirmation nor a denial. The author chose to use the word judgment in a new way.

### What Is a Judgment

The author said that this is not a small question, because:

> the notion of judgement is just about the first of all the notions of logic, the one that has to be explained before all the others, before even the notions of proposition and truth, for instance. There is therefore an intimate relation between the answer to the question what a judgement is and the very question what logic itself is.

He first gave an very simple answer (which is essentially right):

- When understood as an act of judging, it is an act of knowing.
- When understood as that which is judged, it is the object of knowledge.

Then he gave elaboration about the two different act of knowledge:

- to know = to have understood, comprehended, grasped, seen
- to understand, comprehended, grasp, see = to get to know.

And there are some questions:

- is a judgment a judgment already before it is grasped
- or it become a judgment only thorough our act of judging?
  - assuming the later, what should we call a judgement before it has been judged, that is, has become known?

Martin then discussed that why we should make a difference between a judgement before and after it has been proved, and he called the latter as **evident judgment**.

### Summary

> So far, I have said very little about the notions of proposition and truth. The essence of what I have said is merely that to judge is the same as to know, so that an evident judgement is the same as a piece, or an object, of knowledge, in agreement with Bolzano's definition of knowledge as evident judgement.

## Bibliography

Martin-Lof1996 {{< label Martin-Lof1996 bib >}}
: Martin-Löf, P. (1996). On the meanings of the logical constants and the justifications of the logical laws. Nordic Journal of Philosophical Logic, 1(1), 11–60.
