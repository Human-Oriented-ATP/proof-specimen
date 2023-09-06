# Backward-reasoning from hypothesis

_Proofs where backward-reasoning from the hypothesis helps proof discovery_. 

Backward-reasoning from the hypothesis H means finding a statement X such that X ⇒ H.  Equivalently, it means finding statements such that ¬H ⇒ ¬X.  So, this technique can also be thought of as... 

_Proofs where negating the hypothesis and seeing what follows helps proof discovery._

This seems to be a useful technique, because sometimes, not only will the discovered conditions imply the hypothesis, but they will also be implied by it.

### In a metric space, sequential compactness implies compactness.

*High-level:* 
- The key intermediary properties here are that a sequentially compact metric space must be _totally bounded_ and _complete_.  But how do we motivate that?  
- Tim decided to reason backward from the hypothesis (find P such that P ⇒ Q) by reasoning forward from the negation of the hypothesis (finding P such that ¬Q ⇒ ¬P).  So, what do sequences do in a non-sequentially-compact metric space?
- We eventually end up noticing that for a sequence to have no convergent subsequence, we need either (1) that the space is _not_ totally bounded, or (2) the space is _not_ complete.
- We take the contrapositive, and find that the conditions that imply the hypothesis are "total boundeness" combined with "completeness."
- In this way, reasoning backward from the hypothesis leads us to two useful intermediary properties for the proof.

*Details* are in the [full proof that sequential compactness implies compactness][1], the [full proof that compactness implies sequential compactness][2], and the [analysis of the role of backward-reasoning from hypothesis in this problem][3].

[1]:	./seq-implies-compact.pdf
[2]:	./compact-implies-seq.pdf
[3]:	analysis.pdf
