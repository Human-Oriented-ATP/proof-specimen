# Forward-reasoning from target

_Proofs where forward-reasoning from the target helps proof discovery._

### In any n-vertex graph where each vertex’s degree is at least n/2, there exists a Hamiltonian cycle.

*High-level:* 
- When you solve it, you can forward-reason from the target and say “well, if there’s a Hamiltonian cycle, then there’s definitely a Hamiltonian path.”
- As it turns out, the prevailing way to do it (i.e. the way Tim learned it in school, and the way it seems textbooks prove it), involves breaking it up into:
	- Proving there exists a Hamiltonian path (as mentioned before, achieved by forward reasoning).
	- Proving each end-vertex on the path has an edge that connects it with two particular vertices along the path.
	- Proving the Hamiltonian path plus those two new edges can be used to construct a Hamiltonian cycle.

*Details* TBD.

### Consider a commutative ring R. Prove that R/I is a field iff I is a maximal ideal.

*High-level:* The key to one direction of the proof lies in constructing an ideal J such that I ⊊ J ⊊ R.  Forward-reasoning-from-target helps us slowly parameterize the set builder notation for J (the ideal in “between” the given ideal “I” and the full ring “R”):
- We first notice it’s _necessary_ to add in the elements of I…
- Then we notice it’s _necessary_ that it contains one element that’s not in I…
- And then we notice it’s _necessary_ to apply closure.  
	By the time we’ve finished all that, we realize the ideal J we have constructed is _sufficient_ for our proof. 

*Details* are in the [pdf containing the proof][1], and the [pdf containing the analysis of conflict-driven reasoning][2].

### Create the number 19 by adding 4s and 7s

*High-level:* The target is finding a and b such that “4a+7b=19.”  Reasoning forward from the target gets us that since 4a is even, then 7b must be odd, and in turn then b must be odd..and so we narrow the search space.

*Details* are in the [pdf containing the proof][3].

### Cars on a racetrack

There are n cars on a circular track.  Adding up the gas in their tanks, there’s enough to get around the track exactly once.  Show there exists a car that can complete one lap by collecting gas from the others on its way around.

*High-level:* 
- I reasoned forward from the target in this way: “Well, if there is a car that can make it all the way around, then there’s definitely a car that can make it to the next car.”
- And once I had proven that lemma, I could use it to “shrink” the size of the racetrack in an inductive argument.

*Details* are in [the full pdf][4].

### Does there exist a non-abelian group whose subgroups are all normal?

*High-level:* 
- Tim uses forward-reasoning from the target to deduce a bunch of properties that must be satisfied for such a group.   
- In particular, he finds that such a group 
	- must have size at least 8…
	- can’t be a dihedral group…
	- can’t be abelian…
	- so there must be 2 elements that don’t commute…
	- and so then the subgroup generated by a and b will still be non-abelian, because a and b still don’t commute
	- so that subgroup will actually be a smaller such counterexample…
	- so that again whittles down the size of the search space — now you can just consider groups with only 2 generators.
- So you can filter out a bunch of objects while doing a brute force search, or Tim says, “whittle things down with necessary conditions”


*Details* are in [the full pdf][5].


### The four digit number n (written like aabb) is a square.  Find n.
*High-level:* To solve it, Tim reasoned forward from the target and noted that  n = 11(100a+b).  Since it’s a square, and there’s one factor of 11, there must be another factor of 11, so 100a+b is also a multiple of 11.  He continued reasoning forward from the target like this until identifying “n.”

*Details* are in [the full pdf][6].

### Start with four integers (a,b,c,d), where not all four integers are equal, and repeatedly replace it with (a-b,b-c,c-d,d-a).  Show one term in the quadruple will diverge to infinity.
*High-level:*  Fredy noticed that we can solve this problem by reasoning forward from the target to a weaker statement.  We want to show one of the terms does go to infinity.  So  it’s _necessary_ that a^2+b^2+c^2+d^2 gets arbitrarily large. When we prove that necessary statement, and combine it with the fact that a+b+c+d=0 for all but the first term, we have finished the proof.

*Details* are in [the full pdf][7].

### Let H be a subgroup of G.  Show the size of a coset of H is the same as the size of H.
*High-level:*  We want to show (the size of a coset of H) = (the size of H).  Here, it’s helpful to reason forward from the target and say that if that conclusion held, then it is _necessary_ (and as it turns out, equivalent) that the coset must contain no “duplicate” elements.  So, we now look at if there was a “duplicate” element,  we derive a contradiction.

*Details* are in [the full pdf][8].

[1]:	max-ideals.pdf
[2]:	max-ideals-analysis.pdf
[3]:	19-from-4s-and-7s.pdf
[4]:	n-cars.pdf
[5]:	non-abelian-groups.pdf
[6]:	aabb.pdf
[7]:	diverging-tuple.pdf
[8]:	cosets-same-size.pdf