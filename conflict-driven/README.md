# Conflict-Driven Proofs

_Proofs where oscillating between counterexamples, lemmas, and the proof is genuinely helpful._

### On a connected graph (with at least 3 vertices) and no cut vertex, every two vertices are on a cycle.

*High-level:* In trying to come up with counterexamples to the theorem, you come up with all sorts of genuinely helpful lemmas e.g. “two vertices are on a cycle iff there are two disjoint paths between them” and “for any two u-v paths in a graph with no cut vertex, there exists another path that avoids their first point of intersection.”

*Details* are in [the full pdf][1].


### A tree has at most n-1 edges

*High-level:* The prover proves a specialization of the lemma, proving that a graph in which every vertex has degree at least 2 must contain a cycle. The adversary prompts the prover to explain why the proof fails when a particular hypothesis is removed (that is, why the generalization fails).  This adversarial prompting makes the prover realize that leaves are crucial to the proof, and then formulates a relevant lemma about them.

*Details* are in [the full pdf][2].

[1]:	no-cut-vertex-every-two-on-cycle.pdf
[2]:	tree-implies-n-1.pdf