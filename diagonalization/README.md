
# Diagonalization

There are a few proofs that somehow involve (1) implicitly making a countable-by-countable table, and then (2) picking elements along the diagonal of that table.

I split such proofs into two categories:
- (Discrete) These proofs involve some sort of “flipping” of the diagonal elements.  Those proofs often tend to be good for counting arguments…since ultimately the “flipped” element appears nowhere on the initial list.  These proofs can also be generalized to Lawvere’s fixed point theorem, in which this “flipping” function is key.
- (Continuous) Some proofs involve no such flipping, and as such, it’s difficult to imagine how Lawvere’s can generalize them naturally.  But these proofs still involve picking elements along the diagonal.  These proofs often involve having a table of sequences, and then picking a diagonal “subsequence” that has a particular property or converges to a particular value.

There might be some reasonable common generalization of the above two diagonalization proof techniques (and it may even be possibly that Lawvere’s can somehow generalize both), but even if there is, it is likely not very “human” to use that super-abstract proof technique.

Here are some examples of problems that use diagonalization.

# Diagonalizing for Counting, or “Discrete Diagonalization”

The below proofs all could be written to use Lawvere’s fixed point theorem as a key step.

### The powerset of a set A has greater cardinality than the set A.

*High-level:* We suppose there’s a surjection “f” from A to its powerset.  Then for each element a in the set A, there’s a corresponding f(a) in the powerset of A.  Now consider all elements along the “diagonal” — elements where a is an element of f(a).  Then flip it — and imagine elements where a is not an element of f(a).  That set of elements should be in the powerset, and therefore reachable from some a, but by definition it can’t be.  Contradiction.

*Details* of how to apply Lawvere’s theorem to this proof are in the [document describing specializations of Lawvere’s fixed point theorem][1].

### The set of infinite binary sequences is uncountable.

*High-level:* We list out an enumeration of such sequences, and then flip the bits on the diagonal, to end up with a sequence nowhere in the initial enumeration.

*Details* of how to apply Lawvere’s theorem to this proof are in the [document describing specializations of Lawvere’s fixed point theorem][2].


### The reals are uncountable.

*High-level:* The usual proof here is that we have some proposed enumeration of all the real numbers, then going the diagonal, we “flip” each digit to something it is not, and end up with a real number nowhere on that list. Interestingly, Tim mentioned this can be formulated in terms of sequences.   That is, you can start with a sequence that enumerates all the rationals: (x1, x2, x3…).  Then, you find a closed interval of positive length that doesn’t contain x1.  Then, you find a nested closed interval of positive length that doesn’t contain x2.  And so on.  Ultimately, since the intersection of nested, bounded, non-empty closed intervals is non-empty, in the limit, you end up with an interval that contains real numbers, but  contains nothing in the enumeration.  It’s interesting because the “sequential” and “limit” oriented nature of this proof suggests it could fall under “continuous diagonalization” which suggests my categorization isn’t so clear cut.

*Details* of how to apply Lawvere’s theorem to this proof are analogous to the proof that “the set of infinite binary sequences is uncountable” in the [document describing specializations of Lawvere’s fixed point theorem][3].

# Diagonalizing for Converging, or “Continuous Diagonalization”

The general proof technique here is, Tim mentions, as follows:
- You have countably many sequences.
- You have countably many properties you want a new subsequence to satisfy.  You want that new subsequence to have all those properties at the same time.
- It’s often hard to construct that subsequence in one go.  Instead, you can break it up, by creating a bunch of subsequences that satisfy only some properties.
- Then, if you have that for every subsequence, and for every property, there is a further subsequence that has that property, you may be able to get all those properties at once.


### A compact set is totally bounded (i.e. In a compact set, every sequence has a Cauchy subsequence).

*High-level:* We consider a sequence in our set.  Then we divide the set into smaller chunks using the finite subcover hypothesis, then again into smaller chunks using the finite subcover hypothesis, and so on, using pigeonhole each time to know that there is one chunk that must have infinitely many points in the sequence in it.  Since we eventually get a chunk that is arbitrarily small with infinitely many items in the sequence, we can conclude the subsequence we find is Cauchy.

*Details* are in the [proof that a compact set is both totally bounded and complete (and therefore sequentially compact)][4].

### Every bounded sequence in the reals has a convergent subsequence (Bolzano–Weierstrass)

*High-level:* We have a sequence within a bounded interval.  So one half of that interval (still closed, still nonempty, still bounded) must still contain infinitely many points (by pigeonhole).   Then one half of that interval must contain infinitely many points as well.  We continue nesting closed intervals.  We conclude that the interval created in the limit must be non-empty, and so there is some “x” in all the intervals (including the limit), and that “x” must be the limit of the sequence.

*Details* are in the [Wikipedia proof (which contains nice visuals)][5].

[1]:	./discrete-generalization-as-lawvere.pdf
[2]:	./discrete-generalization-as-lawvere.pdf
[3]:	./discrete-generalization-as-lawvere.pdf
[4]:	compact-to-seq-compact.pdf
[5]:	https://en.wikipedia.org/wiki/Bolzano%E2%80%93Weierstrass_theorem#Alternative_proof