# Conflict-driven

_Proofs where oscillating between counterexamples, lemmas-learnt-from-failure, and the proof is genuinely helpful._

### Given any n (even) points on a plane, there exists a line that partitions them into n/2 on one side of the line and n/2 on the other.

*High-level:* By “following our nose”, we eventually *conjecture* that a vertical line, when correctly translated, will work.  However, the *failure* point of this argument is the counterexample of a vertical line that is collinear with two points.  By counting the number of lines (not just vertical ones) that could be collinear with two points, we end up with a *lemma* saying there are at most n choose 2 such lines.  Thus we can pick a line with a slope not in that set, and by translating it correctly, find it must work as a dividing line.

*Details* are in [the full pdf][1].

### Construct a pair of dice that, when rolled and summed, yield the same probability distribution as two normal dice.

*High-level:* We had to figure out what each face of each die looked like.  And every time it felt like there were too many options for labelling, we got unstuck by (1) guessing a number was on a certain dice face, (2) realizing we ended up with a higher probability of rolling a certain value than allowed, and then (3) realizing we needed fewer of that number on that dice face. In summary, there were too many possibilities in the search space, and strengthening the statement artificially narrowed it down.  There was quite a bit of back-and-forth between guessing a number on a face, determining the new probability distribution, failing to meet the distribution requirements, re-guessing, re-calculating the new distribution, and using that new information to make a good new guess. 

*Details* are in [the full solution][2] as well as in [the full analysis of how the puzzle employs conflict-driven learning][3].

### Given a positive integer n \> 6, prove it can be written as the sum of 2 positive integers greater than 1 with no common divisor.

*High-level:* It’s helpful to first weaken to solve the problem for the case where n is odd (and thus can be written as 2k+1), where then the two positive integers with no common divisor that sum to n are (k) and (k+1).  This weakening provides us with a proof plan for the case when n is even, which is more complicated, but we feel comfortable “committing” to the complicated calculations since the proof plan seems viable given the success in the odd case.

*Details* are in [the full pdf][4].

### Suppose you have a continuous function from a compact metric space to the reals.  Does the preimage of an interval have finitely many connected components?

*High-level:* In trying to disprove the statement, we notice _tension_ between (1) making a counterexample function continuous near the point in the domain where you want the infinitely many connected components and (2) the preimage actually having infinitely many connected components.   From this, we now try to prove that you always have finitely many connected components , and use what we’ve _learned_ to try to use that “problem point” in a proof by contradiction (assuming there are infinitely many connected components in the preimage, and then showing the function can’t be continuous at that point). Then we notice _conflict_ in proving that there’s a difficulty defining that function at that point, because as long as the point is defined to map to the endpoint of an interval, we can’t find a contradiction.  From this, we again try to disprove the statement, using what we’ve _learned_ to try to find an example where the point maps to the endpoint of an interval — which ultimately leads to the disproof of the conjecture.

*Details* are in [the full solution][5] as well as in [the full analysis of how the puzzle employs conflict-driven learning][6].

### A graph with no odd cycles is bipartite.

*High-level:* The interesting direction is “no odd cycle implies bipartite.”  So, we take this graph with no odd cycle, and create the forced bipartition (putting one vertex “v” in set A, that vertex’s neighbours in set B, those neighbours in set A, and so on).  Now we want to show that this indeed worked, and there is no edge between vertices in set A and B.  At this point it might be helpful to prove the opposite: to connect two vertices “a” and “a’” both in set A.  But then we run into a conflict — we end up with *odd cycles*.  In particular, the *point of failure* is that the distance from a to v is even, and the distance from v to a’ is even, and the distance from a’ to a is odd.  So, we conjecture that these conditions always hold, and prove that.  We then run into another *failure*: those concatenated paths create an odd circuit, not necessarily an odd cycle.  The *point of failure* is their first intersection point “m.”  But then we see there is always an odd cycle involving a, a’, and m.  And now we’re done.

*Details* are in [the full pdf][7].


### Two people are playing a chess game, when suddenly the wind picks up and blows the white king away.  Given the [board][8], whose turn is it, and where was the white king?

*High-level:* This example is a bit of a departure from typical math theorems -- instead, we have this chess puzzle that Mirek introduced to us.  Nonetheless, it employs the key parts of a “conflict-driven” reasoning process.  In solving this puzzle, we oscillate a lot between asking questions like “could it be white’s turn?” (a conjecture), but then proving it can’t be (a conflict), and then realizing it must be black’s turn (a conflict-inspired lemma), and then reasoning some more to realize that the black king must be in check (making progress on the proof), then asking “could the black bishop have moved to put that king in check” (another conjecture), then proving it can’t be (another conflict), and so then realizing the previous turn must have created a revealed check against the black king (a conflict-inspired lemma), and so on, until we narrow down exactly where the white king must have been.

*Details* are in [the full puzzle and solution][9] as well as in [the full analysis of how the puzzle employs conflict-driven learning][10].



### On a connected graph (with at least 3 vertices) and no cut vertex, every two vertices are on a cycle.

*High-level:* In trying to come up with counterexamples to the theorem, you come up with all sorts of genuinely helpful lemmas e.g. “two vertices are on a cycle iff there are two disjoint paths between them” and “for any two u-v paths in a graph with no cut vertex, there exists another path that avoids their first point of intersection.”  There’s also one statement (“any two vertices u and v will have two disjoint paths between them“) that we strengthen into a stronger-but-false conjecture (“given one path between any two vertices u and v, there will be second path between them that is disjoint to first one”) that leads to a genuinely helpful meta-reasoning step (which is, as Tim mentioned, noticing that he needed to “slowly modify the given path”).

*Details* are in [the full pdf][11].


### A tree has at most n-1 edges

*High-level:* The prover proves a specialization of the lemma, proving that a graph in which every vertex has degree at least 2 must contain a cycle. The adversary prompts the prover to explain why the proof fails when a particular hypothesis is removed (that is, why the generalization fails).  This adversarial prompting makes the prover realize that leaves are crucial to the proof, and then formulates a relevant lemma about them.

*Details* are in [the full pdf][12] and in the [analysis][13] of how this proof uses strengthening.

### Semigroup where BBBC = BBCB

*High-level:* There are lots of mistakes and mistake-inspired-lemmas that can be encountered while working through this problem, e.g.:
- Multiplying an equation by B too many times, and realizing I couldn’t get to a target with less Bs, made me realize that there was no rule to destroy Bs (you could only add them).
- Trying to move a “C” to the front of a term and failing made me realize there was no way to bring a “C” to the front if there is an “A” anywhere before it.
- Not being able to move a “C” to the front of the term, when that was my goal, made me realize that actually I needed to modify my goal to a stronger one where the “C” was destroyed entirely.

*Details* are in [the full pdf][14].


### Prove an r-regular and bipartite graph does not have a bridge

*High-level:* I try to prove the stronger, false statement: that any regular graph does not have a bridge.  But, we find a counterexample, and find there are regular graphs with bridges.  And so now we’re driven to characterize such graphs, and we find all such graphs have a particular degree sequence, and that degree sequence is incompatible with bipartiteness.  And so, we end up proving the contrapositive: regular + bridge =\> not bipartite.

*Details* are in [the full pdf][15].


### Is there a graph with degree sequence 1,3,3,3?

*High-level:* You can prove this doesn’t work either (1) by trying a forced construction of an example, failing to construct such an example, and generalizing the failure to the fact that there is a vertex of degree 1 and more than one vertex of maximal degree, or (2) Proving the stronger statement “there is no n-vertex graph with degree sequence 1, n-1, n-1….”.

*Details* are in [the full pdf][16].


### Either a graph or its complement is connected.

*High-level:* We are trying to prove “if a graph is not connected, its complement must be.”  There are two ways to strengthen this statement:
- Unfolding the definition of connectedness, this really means “If there are  two vertices with * no path* between them in a graph, then the graph’s complement is connected.”  It ends up being useful to weaken the hypothesis (and therefore  strengthen the statement) to  “If there are two vertices with * no path of length 1 or 2* between them in a graph, then the graph’s is connected.”
- Alternately, it could also be useful to strengthen the target (and therefore strengthen) to “If a graph is not connected, its complement is connected *and has diameter at most 3*.”

*Details* are in [the pdf of the proof][17], [a point-and-click proof][18], [analysis of the proof][19], and [ideas for automating the proof.][20]




# The Complement

_Proofs where a conflict-inspired lemma is easily derived, but not helpful to proof discovery._


### Cars on a racetrack

*High-level:* There are lots of *stronger (false)* conjectures to be made here, e.g.:
- Any car that can make it to the next car can make it all the way around the track.
- It’s always the car that has the most gas that works.
- It’s always the car closest to the next car that works.
But I don’t think that disproving any of these conjectures help aid proof discovery.  So, these are some examples where there is not much to learn from failure (disproving a false, stronger statement).

*Details* are in [the full pdf][21].

### Prove an r-regular and bipartite graph does not have a bridge

*High-level:* I tried going by contrapositive: regular + has bridge implies not bipartite.  In the process, I realized I ended up with a graph where I plugged in an even value for the “r” in the regular graph with a bridge, and it *didn’t work*, so I realized from the conflict that *r is odd*.   It then immediately followed that in a n-vertex subgraph formed by taking the biggest connected component after removing the bridge, *n is even*.  But, neither of these facts end up being helpful in the final proof.

*Details* are in [the full pdf][22].

[1]:	bipartition-points-on-plane.pdf
[2]:	dice-proof.pdf
[3]:	dice-analysis.pdf
[4]:	sum-of-coprime.pdf
[5]:	interval-preimage.pdf
[6]:	interval-preimage-analysis-1.pdf
[7]:	no-odd-cycle-bipartite.pdf
[8]:	chess-puzzle.pdf
[9]:	chess-puzzle.pdf
[10]:	chess-puzzle-analysis.pdf
[11]:	no-cut-vertex-every-two-on-cycle.pdf
[12]:	tree-implies-n-1.pdf
[13]:	tree-implies-n-1-analysis.pdf
[14]:	semigroup-bbbc.pdf
[15]:	regular-bipartite-bridge.pdf
[16]:	degree-sequences.pdf
[17]:	graph-or-complement-1-proof.pdf
[18]:	graph-or-complement-2-pointandclick.pdf
[19]:	graph-or-complement-3-analysis.pdf
[20]:	graph-or-complement-4-automation.pdf
[21]:	../forward-from-target/n-cars.pdf
[22]:	regular-bipartite-bridge.pdf