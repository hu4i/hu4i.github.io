---
title: "My Attempts for Studying Formal Methods"
date: 2023-04-07T17:01:45+08:00
draft: false
---

After deciding to study solving cyber security problems via formal methods, I had to self-study much fundamental knowledge from scratch (Because this area is not famous in China, and there are almost no realated courses or textbooks). Learning without guidance is really inefficient, and I’m still not sure if I’m in the right direction. Here are the selected materials (lecture notes, books, papers, etc.) I have learned/studied:

## Basic Views

[*Software Foundations*](https://softwarefoundations.cis.upenn.edu/) is a series of online textbooks that gives me an impressive impression of viewing programming mathematically. It gradually constructs a relatively complex theorem from basic atoms, encouraging you to believe you can prove anything on a computer. Therefore, after finishing reading [*Volume 1: Logical Foundations*](https://softwarefoundations.cis.upenn.edu/lf-current/index.html), I determined to study formal methods.

After reading *[Volume 2: Programming Language Foundations](https://softwarefoundations.cis.upenn.edu/plf-current/index.html)*, **I became interested in Hoare logic. Its idea of only focusing on what’s changed in a program is fresh and amazing.**

But after investigating Hoare logic further, I thought I had to learn the basic knowledge of formal logic:

## Mathematical Logic

When reading this book, *A Mathematical Introduction to Mathematical Logic*[\$^1\$][1], I always got lost in the details of the proofs and exercises. After reading the *Soundness and Completeness Theorems* of first-order logic, **I feel I got a taste of formal logic.** But the remaining topics seem not so accessible to me, and I gave up. But I got interested in the computability theory the book mentions.

## Computability

*Computability and Logic*[\$^2\$][2] is an interesting book that makes you believe you can construct a “computer”(here I mean an abstract machine that can compute) by yourself. **I got a basic comprehension of computability from this book.** It uses rigorous mathematical proof to show the equivalences among different representations of computability. But it also makes me kind of frustrated because I don’t want to believe that our brains may have the possibility to be machines that only carry simple tasks like term rewriting.

## Skimming Through Papers

My tutor suggested me not just to read textbooks but to get a broad view and find a relatively minor topic to study. After reading some Chinese review papers[\$^{3,}\$][3] [\$^{4,}\$][4] [\$^5\$][5], I think that model checking isn’t an elegant method because it’s mainly a search problem. **I believe an elegant way should be comprehensive, not just try out every possibility. Thus I put my efforts into investigating two methods: formal synthesis and formal verification.**

After reading a paper about synthesis[\$^6\$][6], I chose some interesting topics to investigate, like logic programming and deductive synthesis:

- Logic programming

    (Some will say that logic programming is not program synthesis). I read some chapters of a textbook named *Logic Programming with Prolog*[\$^7\$][7]. The idea is that executing the program amounts to proving or refuting the corresponding logical formula. But the kind of logical formula is limited, and how to find a solution to a formula is a search problem.

- Deductive synthesis

    I read a paper named *Theory Exploration Powered by Deductive Synthesis*[\$^8\$][8] and some related materials[\$^{9,}\$][9] [\$^{10,}\$][10] [\$^{11}\$][11]. But it’s also about how to optimize search problems.

I have to admit that I investigated poorly in this area, but I lost interest in this area mostly because of the successful application of machine learning in program generation. And I believe formal verification will be an influential method to check the correctness of the machine-generated code.

But I’m not empty-handed in investigating program synthesis, because I learned an important conception of “constructive”:

## Intuitionistic Logic

During reading papers about program synthesis, “constructive” is always assumed to be known by readers. By searching on the internet, I found a lecture note named [*Constructive Logic*](https://www.cs.cmu.edu/~fp/courses/15317-f00/handouts/logic.pdf). It cites Martin-Löf’s famous paper [\$^{12}\$][12]. After reading this paper and related materials [\$^{13,}\$][13] [\$^{14}\$][14], **I find that it is intuitionistic logic that corresponds to programming language best.** At that time, I could really “touch” the idea of Curry-Howard correspondence.

## Lambda Calculus

I think I should learn formal semantics before lambda calculus. Because when I read the book [\$^{15}\$][15], I could just know that it is a model of computing but didn’t know how important it is and how it can be used in computer science. Therefore, I just read four chapters of that book and only **got the basic ideas of lambda calculus**. I think I should read *Types and Programming Languages* [\$^{16}\$][16] first.

## Hoare Logic and Separation Logic

After investigating program synthesis, I think program verification is more attractive. I read some papers about BI[\$^{17}\$][17] and separation logic[\$^{18,}\$][18] [\$^{20}\$][20]. **I find that separation logic echoes Hoare’s idea because they both narrow the scope concerned and separate unrelated factors out. And use the frame rule to glue everything together.** But there are many improved versions of separation logic, which makes me confused about which one to study first.

## Iris

A senior at Aarhus University told me about Iris. Iris claims to be a general framework of program logic. What surprises me is its successful application in the formal verification of Rust [\$^{19}\$][19].  And I think it may stop the trend that creates different separation logic for different aims.

But, for now, I can only understand the “separation” part of Iris. I still have problems in the “concurrent,” “higher-order,” and “framework” parts. Even worse, I have to systematically learn the formal semantics because there are some definitions that I can’t recognize.

## Formal Semantics

After reading the lecture notes of [*CS 4110  Programming Languages and Logics*](https://www.cs.cornell.edu/courses/cs4110/2020fa/), I found a textbook named *Types and Programming Languages* [\$^{16}\$][16]. **It’s about operational semantics** and introduces things step by step. I read some chapters about it and tried out its exercises in Ocaml.

## The Curry-Howard correspondence

When I could understand the definitions involving semantics, I continued to read the lecture notes of Iris and stuck on the concept of “later modality.” I don’t know where to begin with this concept, but I found Xavier Leroy’s [lecture notes](https://xavierleroy.org/CdF/2018-2019/) mentioned it. It's about the Curry-Howard correspondence and I think it’s a review of formal semantics and programming logic. I’m currently reading it.

## Category Theory

Many materials mentioned category theory, so I’m also studying category theory now.

## What am I doing now?

I’m currently planning to apply for a Ph.D. position to study program logic and want to have some achievements (like papers) during my undergraduate education. I hope I can write my graduate thesis involving this area.

## References

1. <a id=ref1> </a>Enderton, H.B., A Mathematical Introduction to Logic. 2001: Elsevier Science.
2. <a id=ref2> </a>Boolos, G.S., J.P. Burgess, and R.C. Jeffrey, Computability and Logic. 2007: Cambridge University Press.
3. <a id=ref3> </a>Wang J, Z.N., Feng XY, Liu ZM, Overview of Formal Methods. Journal of Software, 2019. 30(1): p. 33-61(in Chinese).
4. <a id=ref4> </a>CCF Formal Methods Technical Committee. Advances and trends on formal methods. In: The Progress Report of Computer Science and Technology in China from 2017 to 2018. Beijing: China Machine Press, 2018. 1-68(in Chinese with English abstract).
5. <a id=ref5> </a> Sheng-Chao, Q., Survey of Research on Program Verification via Separation Logic. Journal of Software, 2017. 28(8): p. 2010-2025(in Chinese with English abstract).
6. <a id=ref6> </a>Basin, D., et al., Synthesis of Programs in Computational Logic, in Program Development in Computational Logic: A Decade of Research Advances in Logic-Based Program Development, M. Bruynooghe and K.-K. Lau, Editors. 2004, Springer Berlin Heidelberg: Berlin, Heidelberg. p. 30-65.
7. <a id=ref7> </a>Bramer, M., Logic Programming with Prolog. 2013: Springer London.
8. <a id=ref8> </a>Singher, E. and S. Itzhaky. Theory Exploration Powered by Deductive Synthesis. 2021. Cham: Springer International Publishing.
9. <a id=ref9> </a>Tate, R., et al., Equality Saturation: A New Approach to Optimization. Popl '09, 2009: p. 264–276.
10. <a id=ref10> </a>Bezem, M., et al., Term Rewriting Systems. 2003: Cambridge University Press.
11. <a id=ref11> </a>Willsey, M., et al., egg: Fast and extensible equality saturation. Proc. ACM Program. Lang., 2021. 5(POPL): p. Article 23.
12. <a id=ref12> </a>Martin-Löf, P., On the meanings of the logical constants and the justifications of the logical laws. Nordic Journal of Philosophical Logic, 1996. 1(1): p. 11-60.
13. <a id=ref13> </a>Per, M.-L., Constructive Mathematics and Computer Programming. Studies in Logic and the Foundations of Mathematics, 1982. 104: p. 153-175.
14. <a id=ref14> </a>D, B. and R. S, Constructive Mathematics in Theory and Programming Practice. Philosophia Mathematica, 1999. 7(1): p. 65-104.
15. <a id=ref15> </a>Hindley, J.R. and J.P. Seldin, Lambda-Calculus and Combinators: An Introduction. 2008: Cambridge University Press.
16. <a id=ref16> </a>Pierce, B.C., Types and Programming Languages. 2002: MIT Press.
17. <a id=ref17> </a>Ishtiaq, S.S. and P.W. O'Hearn, BI as an assertion language for mutable data structures, in Proceedings of the 28th ACM SIGPLAN-SIGACT symposium on Principles of programming languages. 2001, Association for Computing Machinery: London, United Kingdom. p. 14–26.
18. <a id=ref18> </a>O’Hearn, P., J. Reynolds, and H. Yang. Local Reasoning about Programs that Alter Data Structures. in Computer Science Logic. 2001. Berlin, Heidelberg: Springer Berlin Heidelberg.
19. <a id=ref19> </a>Jung, R., Understanding and evolving the Rust programming language.Ph.D. thesis. 2020.
20. <a id=ref20> </a>O'Hearn, P., Separation Logic. Commun. ACM, 2019. 62(2): p. 86–95.

[1]: <#ref1> "Enderton, H.B., A Mathematical Introduction to Logic. 2001: Elsevier Science."
[2]: <#ref2> "Boolos, G.S., J.P. Burgess, and R.C. Jeffrey, Computability and Logic. 2007: Cambridge University Press."
[3]: <#ref3> "Wang J, Z.N., Feng XY, Liu ZM, Overview of Formal Methods. Journal of Software, 2019. 30(1): p. 33-61."
[4]: <#ref4> "CCF Formal Methods Technical Committee. Advances and trends on formal methods. In: The Progress Report of Computer Science and Technology in China from 2017 to 2018. Beijing: China Machine Press, 2018. 1-68(in Chinese with English abstract)."
[5]: <#ref5> "Sheng-Chao, Q., Survey of Research on Program Verification via Separation Logic. Journal of Software, 2017. 28(8): p. 2010-2025(in Chinese with English abstract)."
[6]: <#ref6> "Basin, D., et al., Synthesis of Programs in Computational Logic, in Program Development in Computational Logic: A Decade of Research Advances in Logic-Based Program Development, M. Bruynooghe and K.-K. Lau, Editors. 2004, Springer Berlin Heidelberg: Berlin, Heidelberg. p. 30-65."
[7]: <#ref7> "Bramer, M., Logic Programming with Prolog. 2013: Springer London."
[8]: <#ref8> "Singher, E. and S. Itzhaky. Theory Exploration Powered by Deductive Synthesis. 2021. Cham: Springer International Publishing."
[9]: <#ref9> "Tate, R., et al., Equality Saturation: A New Approach to Optimization. Popl '09, 2009: p. 264–276."
[10]: <#ref10> "Bezem, M., et al., Term Rewriting Systems. 2003: Cambridge University Press."
[11]: <#ref11> "Willsey, M., et al., egg: Fast and extensible equality saturation. Proc. ACM Program. Lang., 2021. 5(POPL): p. Article 23."
[12]: <#ref12> "Martin-Löf, P., On the meanings of the logical constants and the justifications of the logical laws. Nordic Journal of Philosophical Logic, 1996. 1(1): p. 11-60."
[13]: <#ref13> "Per, M.-L., Constructive Mathematics and Computer Programming. Studies in Logic and the Foundations of Mathematics, 1982. 104: p. 153-175."
[14]: <#ref14> "D, B. and R. S, Constructive Mathematics in Theory and Programming Practice. Philosophia Mathematica, 1999. 7(1): p. 65-104."
[15]: <#ref15> "Hindley, J.R. and J.P. Seldin, Lambda-Calculus and Combinators: An Introduction. 2008: Cambridge University Press."
[16]: <#ref16> "Pierce, B.C., Types and Programming Languages. 2002: MIT Press."
[17]: <#ref17> "Ishtiaq, S.S. and P.W. O'Hearn, BI as an assertion language for mutable data structures, in Proceedings of the 28th ACM SIGPLAN-SIGACT symposium on Principles of programming languages. 2001, Association for Computing Machinery: London, United Kingdom. p. 14–26."
[18]: <#ref18> "O’Hearn, P., J. Reynolds, and H. Yang. Local Reasoning about Programs that Alter Data Structures. in Computer Science Logic. 2001. Berlin, Heidelberg: Springer Berlin Heidelberg."
[19]: <#ref19> "Jung, R., Understanding and evolving the Rust programming language.Ph.D. thesis. 2020."
[20]: <#ref20> "O'Hearn, P., Separation Logic. Commun. ACM, 2019. 62(2): p. 86–95."
