---
title: "On the meanings of the logical constants and the justifications of the logical laws"
date: 2023-06-20T13:33:34+08:00
draft: false
mermaid: true
---

These lectures notes {{< cite Martin-Lof1996 >}} are well-known materials of intuitionistic logic and Martin's type theory. But it seems I need more logical and mathematical experiences and knowledge to fully understand these lecture notes. The subtitles like "Historical and Modern Interpretation of Propositions and Assertions" are given thorough my understanding of the contents.

{{< mermaid >}}
flowchart TD
  EvidenceAndKnowledge[Evidence and knowledge, evident and known]
  Judgement[Definition of judgement]
  Proof[Definition of proof]
  Proposition[Definition of proposition]
  Truth[Definition of truth]
  HypotheticalJudgement[Definition of hypothetical judgement]
  HypotheticcalProof[Definition of hypothetical proof]
  RulesOfReferences[Rules of references]
  Forms[Forms of judgement]
  EvidenceAndKnowledge --> Judgement
  Judgement --> Proof
  Judgement --> Forms
  Forms --> Proposition
  Forms --> Truth
  Forms --> HypotheticalJudgement
  HypotheticalJudgement --> HypotheticcalProof
  HypotheticcalProof --> RulesOfReferences
{{< /mermaid >}}

## First Lecture

### Historical and Modern Interpretation of Propositions and Assertions

Before diving into the main topic about logical constants and logical laws, two entities they operate on (propositions and assertions, respectively) must be discussed and determined.

Martin talked about the source and evolution of some logical concepts in the history, I think the key points are:

- The ambiguity of the word judgment: the act of judging and that which is judged.

- The proposition in **old** sense: the (categorical) proposition can be divided into affirmations and denials.

- What sort of thing is it that is affirmed in an affirmation ($A \text{ is true}$) and denied in a denial ($A \text{ is false}$)? That is, what sort of thing is the $A$ here?. The isolation of this concept (what sort of thing is the $A$) was a step which was entirely necessary for the development of modern logic.

Then he pointed that, through the development of logic, the two entities have their meaning that differs from history usage:

{{< admonition type=note title="Modern Usage (not Definition) of Judgements and Propositions" open=true >}}

- Assertions (or judgments): the things we prove, in particular, the premises and conclusion of a logical inference, are no longer propositions in Russell's terminology, but assertions (or judgments).
- Propositions: the things that we combine by means of the logical operations, the connectives and the quantifiers, are not propositions in the old sense, that is, what Russell calls assertions, but what he calls propositions.

{{< /admonition >}}

### Replace Formulae with Propositions

But he hadn't given his attempting at defining the notions of the two entities. To motivate next step, he came up with the rule of disjunction introduction ($A \text{ true}$ is the abbreviation of $A \text{ is true}$):

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

### Double Meaning of Judgment

The author said that the notion of judgement is not a small question, because:

> The notion of judgement is just about the first of all the notions of logic, the one that has to be explained before all the others, before even the notions of proposition and truth, for instance. There is therefore an intimate relation between the answer to the question what a judgement is and the very question what logic itself is.

He first gave an very simple answer (which is essentially right):

{{< admonition type=note title="Double Meaning of A Judgement" open=true >}}

- When understood as an act of judging, it is an act of knowing.
- When understood as that which is judged, it is the object of knowledge.

{{< /admonition >}}

Then he gave elaboration about the two different act of knowledge:

- to know = to have understood, comprehended, grasped, seen
- to understand, comprehended, grasp, see = to get to know.

And there are some questions:

- is a judgment a judgment already before it is grasped
- or it become a judgment only thorough our act of judging?
  - assuming the later, what should we call a judgement before it has been judged, that is, has become known?

Martin then discussed that why we should make a difference between a judgement before and after it has been proved, and he called the latter as **evident judgment**.

{{< admonition type=note title="Definition of Evident Judgement" open=true >}}

A proved Judgement. (Judgement hasn't been defined yes.)

{{< /admonition >}}

### Summary of The First Lecture

> So far, I have said very little about the notions of proposition and truth. The essence of what I have said is merely that to judge is the same as to know, so that an evident judgement is the same as a piece, or an object, of knowledge, in agreement with Bolzano's definition of knowledge as evident judgement.

## Second Lecture

### No Nonexperienced Truths

Under what condition is it correct to make a judgement:

$$
\begin{equation*}
    A \text{ is true}
\end{equation*}
$$

Martin's conclusion was that you must **know** that $A$ is true, then you have the right to make such a judgment. It's not about whether $A$ is true in fact.

> There is no evident judgement whose evidence has not been experienced, and experience it is what you do when you understand, comprehend, grasp, or see it. There is no evidence outside our actual or possible experience of it.

When you make a judgement is amounts to that it is evident to you. That is:

{{< admonition type=note title="Definition of Evident" open=true >}}

- evident = known

When you say some thing is evident, it is known to you.

{{< /admonition >}}

That is, when you make a judgement $A \text{ is true}$, you implicitly say that $\text{I know that } A \text{ is true}$

### Definition of Judgement

At this point, we can give the definition of judgement:

{{< admonition type=note title="Definition of Judgement" open=true >}}

A judgement is what knowledge is expressed by it, that is, what you must know in order to have the right to make, or utter, it.

{{< /admonition >}}

For example, consider the two forms of judgement:

- $A \text{ is a proposition}$
- $A \text{ is true}$

There're two different pieces of knowledge respectively for one needs to know to have the right to make these two judgements. And what you must know doesn't depend on $A$, but only on the **form of the judgement**. Because:

> Quite generally, I may say that a judgement in this sense, that is, a not yet known, and perhaps even unknowable, judgement, is nothing but an instance of a form of judgement, because it is for the various forms of judgement that I lay down what you must know in order to have the right to make a judgement of one of those forms.

The author also gave two figures as examples {{< cite Martin-Lof1996 16-17 >}}.

### What Is a Proof

Martin explained the definition of proof in his opinion:

{{< admonition type=note title="Definition of Proof" open=true >}}

A proof is what makes judgement evident.

{{< /admonition >}}

> Accepting this, that is, that the proof of a judgement is that which makes it evident, we might just as well say that the proof of a judgement is the evidence for it. Thus **proof is the same as evidence**. Combining this with the outcome of the previous discussion of the notion of evidence, which was that it is the act of understanding, comprehending, grasping, or seeing a judgement which confers evidence on it, the inevitable conclusion is that the proof of a judgement is the very act of grasping it. **Thus a proof is, not an object, but an act**. This is what Brouwer wanted to stress by saying that a **proof is a mental construction**, because what is mental, or psychic, is precisely our acts, and **the word construction, as used by Brouwer, is but a synonym for proof**. Thus he might just as well have said that the proof of a judgement is the act of proving, or grasping, it. And the act is primarily the act as it is being performed. Only secondarily, and irrevocably, does it become the act that has been performed.

When speaking of the verb to prove, if a proof is what makes a judgement evident, then, clearly, to prove a judgement is to make it evident, or known:

- to prove = to get to know = to understand, comprehend, grasp, or see
- to have proved = to know = to have understand, comprehend, grasp, or see

When speaking of acquiring and possessing knowledge,

- to get to know = to acquire knowledge
- to know = to possess knowledge

When speaking of the verb to prove and the noun poof,

- to prove = to acquire, or construct, a proof
- to have proved = to possess a proof.

### Immediate and Mediate Proof

Since inference and the proof are the same, and the proof of a judgement is the very act of knowing it.

- If this act is atomic, or indivisible, then the proof is said to be immediate, just like immediate inference (axiom).
- Otherwise, that is, if the proof consists of a whole sequence, or chain, of atomic actions, it is mediate, just like mediate inference.

Since proof and knowledge are the same, the attributes immediate and mediate apply equally well to knowledge.

Since proof constitutes the evidence for a judgement, we also speak of a judgement being immediately and mediately evident, respectively.

- If the proof is immediate, then the judgement is said to be immediately evident. And an immediately evident judgement is what we call an axiom.
- If, on the other hand, the proof which constitutes the evidence for a judgement is a mediate one, so that the judgement is evident, not by itself, but only by virtue of some previously proved judgements, then the judgement is said to be mediately evident.

But Martin suggested: "Instead of applying the attributes immediate and mediate to proof, or knowledge, I might have chosen to speak of intuitive and discursive proof, or knowledge, respectively."

- The proof of an axiom can only be intuitive, which is to say that an axiom has to be grasped immediately, in a single act.
- Thus a discursive proof is one which runs, from premises to conclusion, in several steps.

Immediately evident judgement is unprovable, their proof have to rest intuitive.

### Forms of Judgement And Order of Conceptual Priority

A form of judgement is essentially just what is called a category, not in the sense of category theory, but in the logical, or philosophical, sense of the word. When you came up with a form of judgement, you must explain **what one must know** in order to have the right to make a judgement of that form.

{{< admonition type=note title="Two Forms of Judgement" open=true >}}

- $A \text{ is proposition}$, or briefly, $A \text{ prop}$
- $A \text{ is true}$, or briefly, $A \text{ true}$

{{< /admonition >}}

He then came up with an concept named order of conceptual priority, one concept being conceptually prior to another concept if it. For example:

- the notion of judgement has to come before the notion of proposition
- the notion of logical consequence has to be dealt with before explaining the notion of implication

### What is A Proposition

To define proposition, that is, a form of a judgement, we need to know what knowledge is expressed by a judgement of the form:

- $A \text{ is a proposition}$

In the old sense, proposition is a truth value, something that is true of false. But there are some trouble when coming to the laws for forming quantified propositions:

$$
\begin{prooftree}
\RightLabel{$\qquad$}
\AXC{$A(x)$ prop}
\UIC{$(\forall x) A(x)$ Prop}
\AXC{$A(x)$ prop}
\UIC{$(\exists x) A(x)$ Prop}
\end{prooftree}
$$

But it's not evident for Martin. It is by its very nature subject related:

> We still have no satisfactory explanations which serve to make them evident on this conception of the notion of proposition. And It does not help to restrict the quantifiers, that is, to consider instead the laws:
$$
\begin{prooftree}
\AXC{$(x \in A)$}
\noLine
\UIC{$B(x)$ prop}
\RightLabel{$\qquad$}
\UIC{$(\forall x \in A) B(x)$ prop}
\AXC{$(x \in A)$}
\noLine
\UIC{$B(x)$ prop}
\UIC{$(\exists x \in A) B(x)$ prop}
\end{prooftree}
$$
> Unless we restrict the quantifiers so severely as to take the set $A$ here to be a finite set, that is, to be given by a list of its elements. But, as soon as A is the set of natural numbers, say, you have the full trouble already. Since, as I said earlier, the law of the excluded middle, indeed, all the laws of the classical propositional calculus, are doubtlessly valid on this conception of the notion of proposition, **this means that the rejection of the law of excluded middle is implicitly also a rejection of the conception of a proposition as something which is true or false**. Hence the rejection of this notion of proposition is something which belongs to Brouwer.

But after some references and elaboration, the definition he defined is:

{{< admonition type=note title="Definition of Proposition" open=true >}}

To know a proposition is to know what counts as a verification, solution, fulfilment, or realization of it.

{{< /admonition >}}

### What is the Truth of A Proposition

Assuming $A \text{ prop}$, that is, assuming you know what counts as a verification of $A$. Then the definition of the judgement of the form:

- $A \text{ is true}$ or, briefly, $A \text{ true}$

And the explanation would be that:

{{< admonition type=note title="Definition of Truth" open=true >}}

To know that a proposition is true is to know how to verify it.

{{< /admonition >}}

### Summary of The Second Lecture

The author discussed and explained judgement and  the two forms of categorial judgement $A \text{ prop}$ and $A \text{ true}$. To know the first form is to posses the knowledge of **what** to do, and to know the second is to knowledge of  **how** to do. And, of course, there can be no question of knowing how to do something before you know what it is that is to be done. So you must know $A$ is a proposition before you know $A$ is true.

## Third Lecture

### Truth and Provability

Are there propositions which are true, but which cannot be proved to be true?

Martin's answer is no. He explained it by demonstrating the two judgements are mutually derivable:

- $A \text{ is true}$
- $(A \text{ is true}) \text{ is provable}$

His proof is (of course, under the assumption that $A$ is a proposition):

- $A \text{ is true} \Rightarrow (A \text{ is true}) \text{ is provable}$: It's by the principle that if something has been done, then it can be done.
- $(A \text{ is true}) \text{ is provable} \Rightarrow A \text{ is true}$: Just put you knowledge of the premise into practice, then you get the conclusion.

My interpretation is:  making the first judgement is to say "I have the knowledge of how to verify $A$". And making the second is to say "I know how to prove that I have the knowledge of how to verify $A$".

### Hypothetical Judgement

Martin discussed the validity of assuming you know something, or to say, you have proved it. You can assume any instance of a form of judgement, which gives rise to the notion of hypothetical judgement (or logical consequence) and the notion of hypothetical proof. We should be carefully distinguished hypothetical judgement from implication.

#### A Simple Form of Hypothetical Judgement

First he gave a simple form of hypothetical judgement:

{{< admonition type=note title="A Simple Form of Hypothetical Judgement for Proposition" open=true >}}

The judgement below

$$
\begin{equation*}
A_1 \text{ true}, ..., A_n \text{ true} \mid A \text{ prop} \tag{1}\label{1}
\end{equation*}
$$

says the $A$ is a proposition under the assumptions that $A_1, ..., A_n$ are all true, and

$$
\begin{equation*}
A_1 \text{ true}, ..., A_n \text{ true} \mid A \text{ true} \tag{2}\label{2}
\end{equation*}
$$

says the proposition $A$ is true under the assumptions that $A_1, ..., A_n$ are all true.

We use the vertical bar $\mid$ for the relation of logical consequence sign here. What stands to the left of the sign, we call the **hypotheses** (or antecedents), in which case what follows the consequence sign is called the **thesis** (or consequent).

But for the the generalization that something being a proposition may depend on other things being true, to make the judgment $\ref{1}$ make sense, we must presuppose:

$$
\begin{align*}
& A_1 \text{ prop} \\\\
& A_1 \text{ true} \mid A_2 \text{ prop} \\\\
& \vdots \\\\  
& A_1 \text{ true}, ..., A_{n-1} \text{ true} \mid A_n \text{ prop}
\end{align*}
$$

To make judgement $\ref{2}$ make sense, except assumptions of $\ref{1}$, we also need to assume the judgement $\ref{1}$ to be evident:

$$
\begin{align*}
A_1 \text{ true}, ..., A_n \text{ true} \mid A \text{ prop}
\end{align*}
$$

{{< /admonition >}}

#### Hypothetical Judgement with Free Variables

Like the two forms above, here are the forms with free variables:

$$
\begin{equation*}
A_1 (x_1, ..., x_m) \text{ true}, ..., A_n (x_1, ..., x_m) \text{ true} \mid_{x_1, ..., x_m} A(x_1, ..., x_m) \text{ prop}
\end{equation*}
$$

and

$$
\begin{equation*}
A_1 (x_1, ..., x_m) \text{ true}, ..., A_n (x_1, ..., x_m) \text{ true} \mid_{x_1, ..., x_m} A(x_1, ..., x_m) \text{ true}.
\end{equation*}
$$

### Hypothetical Proof

To justify the judgements above, we must clarify what constitutes knowledge, or proof, of such a judgement:

{{< admonition type=note title="Hypothetical proof" open=true >}}

The notion of hypothetical proof is a primitive notion, it is a proof of the thesis of a hypothetical judgement from hypotheses. That is to say, when supplemented by proofs of the hypotheses, it becomes a (categorial) proof of the thesis.

{{< /admonition >}}

For example, for the hypothetical judgement

$$
\begin{align*}
A_1 \text{ true}, ..., A_n \text{ true} \mid A \text{ prop},
\end{align*}
$$

the defining property of its hypothetical proof

$$
\begin{matrix}
A_1 \text{ true} & \cdots & A_n \text{ true} \\\\
\vdots & & \vdots \\\\
& A \text{ prop} &
\end{matrix}
$$

is that, when it is supplemented by proofs

$$
\begin{matrix}
\vdots & \dots & \vdots \\\\
A_1 \text{ true} & & A_n \text{ true}
\end{matrix}
$$

of the hypotheses, or antecedents, it becomes a proof

$$
\begin{matrix}
\vdots & & \vdots \\\\
A_1 \text{ true} & \cdots & A_n \text{ true} \\\\
\vdots & & \vdots \\\\
& A \text{ prop} &
\end{matrix}
$$

of the thesis.

Similarly for the judgement of the second form:

$$
\begin{align*}
A_1 \text{ true}, ..., A_n \text{ true} \mid A \text{ true}
\end{align*}
$$

For the free variable version, the hypothetical proof is proof which becomes a categorical proof of the thesis when you first substitute arbitrary expressions $a_1, ..., a_m$, of the same respective arities as the variables $x_1, ..., x_m$, for those variables, and then supplement it with proofs of the hypotheses.

### Rules of Inference

Then we can talk about the rules of inference, or proof rules, and their **semantical explanations**.

#### Rules for Implication

{{< admonition type=note title="Implication Formation" open=true >}}

$\supset\text{-formation}.$

$$
\begin{prooftree}
\AXC{$A \text{ prop}$}
\AXC{($A \text{ true})$}
\noLine
\UIC{$B \text{ prop}$}
\BIC{$A \supset B \text{ prop}$}
\end{prooftree}
$$

This rule is a rule of immediate inference and it says that, if $A$ is a proposition and $B$ is a proposition provided that $A$ is true, then $A \supset B$ is a proposition.

What the judgement  $A \supset B \text{ prop}$ is what counts as a verification of $A \supset B$ is, so the explanation is: the verification is a hypothetical proof

$$
\begin{matrix}
  A \text{ true} \\\\
  \vdots \\\\
  B \text{ true}
\end{matrix}
$$

that $B$ is true under the assumption that $A$ is true.

{{< /admonition >}}

The second premise of $\supset\text{-formation}.$ is actually a logical consequence (hypothetical judgement):

$$
\begin{equation*}
A \text{ true} \mid B \text{ prop}
\end{equation*}
$$

{{< admonition type=question title="Question" open=true >}}

Does the $A \supset B \text{ prop}$ has the same proof with the hypothetical judgement $A \text{ true} \mid B \text{ prop}$? Because when you assume $A \text{ true}$, you must also assume $A \text{ prop}$

{{< /admonition >}}

{{< admonition type=note title="Implication Introduction" open=true >}}

$\supset\text{-introduction}.$

$$
\begin{prooftree}
\AXC{($A \text{ true})$}
\noLine
\UIC{$B \text{ prop}$}
\UIC{$A \supset B \text{ prop}$}
\end{prooftree}
$$

This is a rule of immediate inference. And, obviously, to get the conclusion of introduction rule, you must presuppose both the premises of formation rule and the premises of introduction rule. Similarly for all other rules.

*Explanation*. Its justification rests again on the principle that, if something has been done, then it can be done.

{{< /admonition >}}

{{< admonition type=note title="Implication Elimination" open=true >}}

$\supset\text{-elimination}.$

$$
\begin{prooftree}
\AXC{$A \supset B \text{ true}$}
\AXC{$A \text{ true}$}
\BIC{$B \text{ true}$}
\end{prooftree}
$$

This is a rule of immediate inference.

*Explanation*. The principle is that, if you supplement a hypothetical proof with proofs of its hypotheses, then you get a proof of its conclusion. This is in the nature of a hypothetical proof: it is that property which makes a hypothetical proof into what it is.

{{< /admonition >}}

### Rules of Conjunction

{{< admonition type=note title="Conjunction Formation" open=true >}}

$\\&\text{-formation}.$

$$
\begin{prooftree}
\AXC{$A \text{ prop}$}
\AXC{$B \text{ prop}$}
\BIC{$A \\& B \text{ prop}$}
\end{prooftree}
$$

*Explanation*. The explanation is that a verification of $A \\& B$ consists of a proof that $A$ is true and a proof that $B$ is true:

$$
\begin{matrix}
\vdots & \text{and} & \vdots \\\\
A \text{ true}  & & B \text{ true}.
\end{matrix}
$$

{{< /admonition >}}

{{< admonition type=note title="Conjunction Introduction" open=true >}}

$\\&\text{-introduction}.$

$$
\begin{prooftree}
\AXC{$A \text{ true}$}
\AXC{$B \text{ true}$}
\BIC{$A \\& B \text{ true}$}
\end{prooftree}
$$

{{< /admonition >}}

{{< admonition type=note title="Conjunction Elimination" open=true >}}

$\\&\text{-Elimination}.$

$$
\begin{prooftree}
\RightLabel{$\qquad$}
\AXC{$A \\& B \text{ true}$}
\UIC{$A \text{ true}$}
\AXC{$A \\& B \text{ true}$}
\UIC{$B \text{ true}$}
\end{prooftree}
$$

{{< /admonition >}}

### Rules of Disjunction

{{< admonition type=note title="Disjunction Formation" open=true >}}

$\lor\text{-formation}.$

$$
\begin{prooftree}
\AXC{$A \text{ prop}$}
\AXC{$B \text{ prop}$}
\BIC{$A \lor B \text{ prop}$}
\end{prooftree}
$$

*Explanation*. The explanation is that a verification of $A \\& B$ consists of a proof that $A$ is true or a proof that $B$ is true:

$$
\begin{matrix}
\vdots & \text{or} & \vdots \\\\
A \text{ true}  & & B \text{ true}.
\end{matrix}
$$

{{< /admonition >}}

{{< admonition type=note title="Disjunction Introduction" open=true >}}

$\lor\text{-introduction}.$

$$
\begin{prooftree}
\RightLabel{$\qquad$}
\AXC{$A \text{ true}$}
\UIC{$A \lor B \text{ true}$}
\AXC{$B \text{ true}$}
\UIC{$A \lor B \text{ true}$}
\end{prooftree}
$$

{{< /admonition >}}

{{< admonition type=note title="Disjunction Elimination" open=true >}}

$\lor\text{-Elimination}.$

$$
\begin{prooftree}
\AXC{$A \lor B \text{ true}$}
\AXC{$(A \text{ true})$}
\noLine
\UIC{$C \text{ true}$}
\AXC{$(B \text{ true})$}
\noLine
\UIC{$C \text{ true}$}
\TIC{$C \text{ true}$}
\end{prooftree}
$$

{{< /admonition >}}

### Rules of Falsehood

{{< admonition type=note title="Falsehood Formation" open=true >}}

$\bot\text{-formation}.$

$$
\begin{equation*}
\bot \text{ prop}
\end{equation*}
$$

*Explanation*. This is an axiom. The explanation is that there is nothing that counts as a verification of the proposition. Under no condition is it true.

{{< /admonition >}}

There is no introduction rule for Falsehood, because there is no verification and it follows you can't know how to proof it.

{{< admonition type=note title="Falsehood Elimination" open=true >}}

$\bot\text{-elimination}.$

$$
\begin{prooftree}
\AXC{$\bot \text{ true}$}
\UIC{$C \text{ true}$}
\end{prooftree}
$$

$C$ is presupposed to be a proposition, not outright, but merely under the assumption that $\bot$ is true.

*Explanation*. This is something that you can safely undertake, because, by the definition of falsehood, there is nothing that counts as a verification of $\bot$. Hence $\bot$ is false, that is, cannot be verified, and hence it is impossible that you ever be provided with a proof that $\bot$ is true.

{{< /admonition >}}

{{< admonition type=question title="Question" open=true >}}

Is this rule valid?

$$
\begin{prooftree}
\AXC{$\bot \text{ true}$}
\UIC{$C \text{ prop}$}
\end{prooftree}
$$

And can $C$ be an incomplete expression here?

{{< /admonition >}}

### Nominal Definition of Negation

{{< admonition type=note title="Nominal definition of Not" open=true >}}

We define negation of $A$ as $A \supset \bot$, abbreviated as $\sim \\!\\! A$.

*Explanation*. Since $A$ is false if and only if $\sim \\!\\! A$ is true.

{{< /admonition >}}

Martin's comment:

> But you **should not** tempt to define the **notion of denial** by saying that $A \text{ is false}$ means that $\sim \\!\\! A \text{ is true}$. The proposition $A$ is false means that it is impossible to verify $A$, and this is a notion which cannot be reduced to the notions of negation, negation of propositions, that is, and truth. **Denial comes before negation in the order of conceptual priority**.

In my point of view, this means: you shouldn't use $\sim \\!\\! A$ to define $A \text{ is false}$. Because we chose to use the notion of denial ($A \text{ is false}$) to define the notion of negation ($\sim \\!\\! A$) first.

### Absolute Consistency

The judgement

$$
\begin{equation*}
  (\bot \text{ is true}) \text{ is unprovable}
\end{equation*}
$$

can be used to express absolute consistency.

My understanding is: for any formal system in which any of its formal proof is a chain of formally immediate inferences and those immediate inferences are instances of of the inference rules in the system. If there is a formal proof of $\bot \text{ is true}$, then there must be one or more incorrect inference rules that violate this absolute consistency.

### Rules of Universal Quantification

{{< admonition type=note title="Universal Quantification Formation" open=true >}}

$\forall\text{-formation}.$

$$
\begin{prooftree}
\AXC{$A(x) \text{ prop}$}
\UIC{$\forall A(x) \text{ prop}$}
\end{prooftree}
$$

*Explanation.* The verification of $\forall A(x) \text{ prop}$ consists of a free variable proof of $A(x) \text{ true}$.

{{< /admonition >}}

{{< admonition type=note title="Universal Quantification Introduction" open=true >}}

$\forall\text{-introduction}.$

$$
\begin{prooftree}
\AXC{$A(x) \text{ true}$}
\UIC{$\forall A(x) \text{ true}$}
\end{prooftree}
$$
{{< /admonition >}}

{{< admonition type=note title="Universal Quantification Elimination" open=true >}}

$\forall\text{-elimination}.$

$$
\begin{prooftree}
\AXC{$\forall A(x) \text{ true}$}
\UIC{$A(a) \text{ true}$}
\end{prooftree}
$$

where $a$ is an expression of the same arity as the variable $x$.

{{< /admonition >}}

### Rules of Existential Quantification

{{< admonition type=note title="Existential Quantification Formation" open=true >}}

$\exists\text{-formation}.$

$$
\begin{prooftree}
\AXC{$A(x) \text{ prop}$}
\UIC{$\exists A(x) \text{ prop}$}
\end{prooftree}
$$

*Explanation.* The verification of $\exists A(x) \text{ prop}$ consists of a proof of $A(a) \text{ true}$ where $a$ is an expression of the same arity as the variable $x$.

{{< /admonition >}}

{{< admonition type=note title="Existential Quantification Introduction" open=true >}}

$\exists\text{-introduction}.$

$$
\begin{prooftree}
\AXC{$A(a) \text{ true}$}
\UIC{$\exists A(x) \text{ true}$}
\end{prooftree}
$$
{{< /admonition >}}

{{< admonition type=note title="Existential Quantification Elimination" open=true >}}

$\exists\text{-elimination}.$

$$
\begin{prooftree}
\AXC{$\exists A(x) \text{ true}$}
\AXC{$(A(x) \text{true})$}
\noLine
\UIC{$C \text{ true}$}
\BIC{$C \text{ true}$}
\end{prooftree}
$$

where $a$ is an expression of the same arity as the variable $x$.

{{< /admonition >}}

### Summary of The Third Lecture

Martin first demonstrated the equality of making a statement about the truth and the provability of a proposition. Then he gave the definition of hypothetical judgement and justified it by defining hypothetical proof. Finally he fulfilled the aim of defining the meanings of the logical constants and the justfying of the logical laws:

> As you have seen, the explanations of the meanings of the logical constants are precisely the explanations belonging to the formation rules. And the justifications of the logical laws are the explanations belonging to the introduction and elimination rules, which are the rules that we normally call rules of inference.

## Summary

He marked that:

> For lack of time, **I have only been able to deal with the pure logic in my semantical explanations**. To develop some interesting parts of mathematics, you also need axioms for ordinary inductive definitions, in particular, axioms of computation and axioms for the natural numbers. And, if you need predicates defined by transfinite, or generalized, induction, then you will have to add the appropriate formation, introduction, and elimination rules for them.

He pointed the difference between his treatment on consistency of a formal system and Hilbert's:

> I have already explained how you see the consistency of a formal system of correct inference rules, that is, the impossibility of constructing a proof
> $$
> \begin{matrix}
> \vdots \\\\
> \bot \text{ true}
> \end{matrix}
> $$
> that falsehood is true which proceeds according to those rules, not by studying metamathematically the proof figures divested of all sense, as was Hilbert's program, but by doing just the opposite: not divesting them of sense, but endowing them with sense.

But I don't quite understand the comment:

> But no longer do we need to prove anything, that is, no longer do we need to prove metamathematically that the proof figures, divested of sense, reduce to introductory form. Instead of proving it, we endow the proof figures with sense, and then we see it! Thus the definition of convertibility, or computability, and the proof of normalization have been transposed into genuine semantical explanations which allow you to see this, just as you can see consistency semantically.

## Bibliography

Martin-Lof1996 {{< label Martin-Lof1996 bib >}}
: Martin-Löf, P. (1996). On the meanings of the logical constants and the justifications of the logical laws. Nordic Journal of Philosophical Logic, 1(1), 11–60.
