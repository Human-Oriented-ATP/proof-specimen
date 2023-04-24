# Induction

_Proofs where applying mathematical induction is genuinely helpful.  This tends to coincide with proofs where applying an algorithm is genuinely helpful. In particular, there are some proofs where there’s an algorithm that solves the problem.  Then the algorithm can sometimes be turned into an inductive argument.  And in some cases, it’s helpful to turn that inductive argument into a closed form._


### Every path is bipartite

*High-level:* You apply a forced construction *algorithm* to create the bipartition — you choose the leaf node to be, arbitrarily, in part A, then its neighbour is forced to be in part B, and its neighbour in A, and so on, and eventually you have a complete partition.  You then turn this into an *inductive* argument saying if the nth node is in part A, then the (n+1)st node is in part B, and vice versa .  And in order to prove the graph is bipartite, you need a *closed-form*, which says for the nth node, if n is even, is in part A, and otherwise in part B.  

*Details* TBD.

### The “half mean value theorem” for graphs (Every graph with average degree at least d has a subgraph with minimum degree at least d/2).

*High-level:* This problem is solved by an algorithm that removes a vertex with degree less than d/2 from the graph, and keeps removing such a vertex until every node has degree at least d/2 (that is, the subgraph is achieved).  The proof for why this leaves you with a non-empty graph at the end involves showing that average degree always stays above d/2 each time you remove a low-degree (i.e. \< d/2 degree) vertex, and once you’ve plucked away enough vertices that you’re left with d/2+1 vertices but still have average degree at least d/2, you must have the complete d/2-regular graph, and thus the minimum degree is at least d/2.

*Details* TBD.
