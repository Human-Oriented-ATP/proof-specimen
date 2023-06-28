# Oscillation

_Proofs where oscillating between counterexamples, lemmas-learnt-from-failure, and the proof is genuinely helpful. ”_

### A graph with no odd cycles is bipartite.

*High-level:* The interesting direction is “no odd cycle implies bipartite.”  So, we take this graph with no odd cycle, and create the forced bipartition (putting one vertex “v” in set A, that vertex’s neighbours in set B, those neighbours in set A, and so on).  Now we want to show that this indeed worked, and there is no edge between vertices in set A and B.  At this point it might be helpful to prove the opposite: to connect two vertices “a” and “a’” both in set A.  But then we run into a conflict — we end up with *odd cycles*.  In particular, the *point of failure* is that the distance from a to v is even, and the distance from v
 to a’ is even, and the distance from a’ to a is odd.  So, we conjecture that these conditions always hold, and prove that.  We then run into another *failure*: those concatenated paths create an odd circuit, not necessarily an odd cycle.  The *point of failure* is their first intersection point “m.”  But then we see there is always an odd cycle involving a, a’, and m.  And now we’re done.

*Details* are in [the full pdf][1].


### Given any n (even) points on a plane, there exists a line that partitions them into n/2 on one side of the line and n/2 on the other.

*High-level:* By “following our nose”, we eventually *conjecture* that a vertical line, when correctly translated, will work.  However, the *failure* point of this argument is the counterexample of a vertical line that is collinear with two points.  By counting the number of lines (not just vertical ones) that could be collinear with two points, we end up with a *lemma* saying there are at most n choose 2 such lines.  Thus we can pick a line with a slope not in that set, and by translating it correctly, find it must work as a dividing line.

*Details* are in [the full pdf][2].


### On a connected graph (with at least 3 vertices) and no cut vertex, every two vertices are on a cycle.

*High-level:* In trying to come up with counterexamples to the theorem, you come up with all sorts of genuinely helpful lemmas e.g. “two vertices are on a cycle iff there are two disjoint paths between them” and “for any two u-v paths in a graph with no cut vertex, there exists another path that avoids their first point of intersection.”

*Details* are in [the full pdf][3].


### A tree has at most n-1 edges

*High-level:* The prover proves a specialization of the lemma, proving that a graph in which every vertex has degree at least 2 must contain a cycle. The adversary prompts the prover to explain why the proof fails when a particular hypothesis is removed (that is, why the generalization fails).  This adversarial prompting makes the prover realize that leaves are crucial to the proof, and then formulates a relevant lemma about them.

*Details* are in [the full pdf][4].

# The Complement

_Proofs where disproving counterexamples is not helpful in proof discovery._

### Cars on a racetrack

*High-level:* There are lots of *stronger (false)* conjectures to be made here, e.g.:
- Any car that can make it to the next car can make it all the way around the track.
- It’s always the car that has the most gas that works.
- It’s always the car closest to the next car that works.
But I don’t think that disproving any of these conjectures help aid proof discovery.  So, these are some examples where there is not much to learn from failure (disproving a false, stronger statement).

*Details* are in [the full pdf][5].

[1]:	no-odd-cycle-bipartite.pdf
[2]:	bipartition-points-on-plane.pdf
[3]:	no-cut-vertex-every-two-on-cycle.pdf
[4]:	tree-implies-n-1.pdf
[5]:	../forward-from-target/n-cars.pdf