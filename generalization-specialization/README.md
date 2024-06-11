# Generalization - Specialization

_Proofs where applying generalization & specialization is genuinely helpful._

### The Dinitz Conjecture

*High-level:* You *generalize* the problem about Latin squares to a problem about graphs, which you then *specialize* to a problem about directed graphs, and so on.

*Details* are in the paper [The Method of Undetermined Generalization and Specialization Illustrated with Fred Galvin's Amazing Proof of the Dinitz Conjecture][1].

### A tree has at most n-1 edges

*High-level:* The prover proves a specialization of the lemma, proving that a graph with every vertex of at least degree 2 must contain a cycle. The adversary prompts the prover to explain why the proof fails when a particular hypothesis is removed (that is, why the generalization fails).  This adversarial prompting makes the prover realize that leaves are crucial to the proof, and then formulates a relevant lemma about them.

*Details* are in [the full pdf][2].

### n is not prime =\> 2^n-1 is not prime

*High-level:* You might start by *specializing* and coming up with an example e.g. with n=6, you trying to factorize `2^(2*3)-1`.  Then you *generalize* when you see that what helps you factorize is that you have something of the form `x^3-1`.  So you *generalize* more in order to retrieve the result in the library that `x^n-1` factorizes.  And then you plug that back in to finish the problem.

*Details* TBD.

### Is there a solution to e^ (√ x) + e^(∛ x)=17?

*High-level:* Tim mentioned it might be a problem that someone, coming straight out of high school, might struggle with. But it helps to weaken the hypothesis (and therefore *generalize* the statement) by turning the whole left hand side to a continuous function $f(x)$.  And then you can realize you can use intermediate value theorem to realize there must be a solution, since at some point the continuous function takes on a value less than 17, and at some point it takes on a value greater than 17.  That is, the information about “e” just distracts you, and it’s more helpful to generalize it away.

*Details* are in [the full pdf][3].

### Can you generate all Mobius transformations by inverses and translations?

*High-level:* So, we want to compose  inverses and translations to create a scaling map.  And to find Mobius transformation that scales by an arbitrary $a$, we want a map that sends sends 0 to 0, 1 to a, and infinity to infinity.
- In this process, it’s helpful to *generalize* by dropping one of the requirements, and instead just find a non-trivial map that fixes 0 and infinity.
- It’s also helpful to *generalize* the resulting function we get (which fixes 1) to a function that sends 1 to -b^2 for a particular b.

*Details* are in [the full pdf][4].

### An inequality in probability

*High-level:* A probability inequality can be more generally stated (and more easily proved) after we reduce reliance on constants (e.g. create a new random variable Y that takes on two existing values with equal probability) and add symmetry (shift Y to be a symmetric random variable).

*Details* are in [the full pdf][5].

[1]:	https://arxiv.org/abs/math/9506215
[2]:	../conflict-driven/tree-implies-n-1.pdf
[3]:	exponential-equals-17.pdf
[4]:	mobius.pdf
[5]:	probability-ineq.pdf