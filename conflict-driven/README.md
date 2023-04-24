# Conflict-Driven Proofs

_Proofs where oscillating between counterexamples, lemmas, and the proof is genuinely helpful._

### Given any n (even) points on a plane, there exists a line that partitions them into n/2 on one side of the line and n/2 on the other.

*High-level:* By “following our nose”, we eventually *conjecture* that a vertical line, when correctly translated, will work.  However, the *failure* point of this argument is the counterexample of a vertical line that is collinear with two points.  By counting the number of lines (not just vertical ones) that could be collinear with two points, we end up with a *lemma* saying there are at most n choose 2 such lines.  Thus we can pick a line with a slope not in that set, and by translating it correctly, find it must work as a dividing line.

*Details* are in [the full pdf][1].


### On a connected graph (with at least 3 vertices) and no cut vertex, every two vertices are on a cycle.

*High-level:* In trying to come up with counterexamples to the theorem, you come up with all sorts of genuinely helpful lemmas e.g. “two vertices are on a cycle iff there are two disjoint paths between them” and “for any two u-v paths in a graph with no cut vertex, there exists another path that avoids their first point of intersection.”

*Details* are in [the full pdf][2].


### A tree has at most n-1 edges

*High-level:* The prover proves a specialization of the lemma, proving that a graph in which every vertex has degree at least 2 must contain a cycle. The adversary prompts the prover to explain why the proof fails when a particular hypothesis is removed (that is, why the generalization fails).  This adversarial prompting makes the prover realize that leaves are crucial to the proof, and then formulates a relevant lemma about them.

*Details* are in [the full pdf][3].

[1]:	bipartition-points-on-plane.pdf
[2]:	no-cut-vertex-every-two-on-cycle.pdf
[3]:	tree-implies-n-1.pdf