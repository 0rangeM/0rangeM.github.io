# Understanding Equivalences

In the late 1950s, Kiiti Morita characterised a relationship between rings that became known as *[Morita equivalence](https://en.wikipedia.org/wiki/Morita_equivalence)*. It is defined as follows. To each ring $R$, we can associate a category: its category of (left) modules. If I have two rings $R$ and $S$, I can ask whether these categories are equivalent, and if so, I say $R$ and $S$ are Morita equivalent. Morita's theorem tells us that this happens if and only if there exist a special pair of bimodules for $R$ and $S$, which determine and are determined by the functors forming the equivalence.

As John Baez [astutely observes](https://twitter.com/johncarlosbaez/status/1254444148016312320), faced with this nice result, a category theorist such as myself is inclined to ask "What is this an example of?" Indeed, there are equivalences of this kind (that is, equivalences of associated categories) for all sorts of mathematical objects, and they are usually called Morita equivalences in honour of Morita's work for rings. In this post, I stretch the analogy further: I examine a general class of problems, explain how these give rise to "Morita-equivalence-type problems", and explain how the more general strategy gives us an approach to solving them.

## Constructions and Markings

Suppose we have a family of mathematical objects $X$, and a construction (of a category or some other kind of object) $D(X)$ for each $X$. At this point, the category theorist again asks:

> What is $D(X)$ an example of?

This amounts to finding a definition of a class of objects $A$ which every $D(X)$ is a member of. There isn't a unique correct answer to this problem: you may care about some essential features of the $D(X)$s more than others, and you may want some other existing constructions to fall under the umbrella of objects in the class $A$. In some cases the $D(X)$s will be instances of a type of mathematical object that is already well-studied, in which case that is a good starting point. Also, one typically aims for (pseudo-)functoriality, choosing a definition such that transformations between $X$s give structure-preserving transformations between the $D(X)$s (although this isn't always possible: take the case of automorphism groups of your favourite class of mathematical objects, for example).

Once you've chosen the definition of a class of objects $A$ that the $D(X)$ are examples of, each notion of equivalence of $A$s (yes, there may be several: see the examples below) gives a 'generalised Morita equivalence' for $X$s! When the construction of the $D(X)$s is functorial, we can view it as an assignment of invariants to $X$s. In this light, the Morita equivalence problem is measures the "strength" of the invariant: equivalent $X$s should give equivalent $D(X)$s, but there may be more equivalences between the $D(X)$s. The more there are of the latter, the less we know about each $X$ given its corresponding $D(X)$, but this loss of information may make $D(X)$ easier to calculate or manipulate, which is incredibly helpful when trying to understand complicated objects. If this sounds familiar, it's because it's a story that's pervasive in modern mathematics, forming the basis of algebraic topology and algebraic geometry.

I presented the Morita equivalence straight away because it was the motivation for this blog post. However, I personally think a far more natural follow-up question once we've chosen our class of objects $A$ is:

> Given an arbitrary $A$, how can I tell whether it's (equivalent to) a $D(X)$?

Examples of these questions are "which abelian categories are categories of modules over a ring?", "which categories/toposes are Grothendieck toposes?"... A constructive answer to such a question identifies the necessary and sufficient structure and data in/on an $A$ which we know to be of the form $D(X)$ and constructs an $X$ presenting it from that data. Let's call this collected structure and data '*markings* on an *A*'. The full result is then of the form "An $A$ is equivalent to a $D(X)$ if and only if it admits markings". As a corollary, we obtain a solution to the *reconstruction problem*:

> Given a $D(X)$ and markings on $D(X)$, how far can we reconstruct $X$?

In the case of the category of modules of a ring $R$, the ring itself is equipped with the structure of a left $R$-module with some very particular properties, and any object with those properties produces a ring with an equivalent category of modules. Thus the marking on an abelian category that identifies it as a category of modules is a choice of such an object, and the canonical choice for a given ring $R$ allows us to recover $R$ precisely.

In a similar vein, the continuous actions of a topological group on sets (treated as discrete spaces) produces an atomic topos. This topos comes equipped with a surjective point whose inverse image functor is the forgetful functor. Given any suitable surjective point, we recover a topological group with an equivalent topos of actions from the natural automorphisms of that point; thus the marking in this case consist of a choice of surjective point. However, while the automorphism group of the point corresponding to a particular presentation $G$ admits a homomorphism from the original group, it is distinct in general; see the 'Complete Topological Groups' section of [this paper](https://arxiv.org/abs/1301.0300) by my PhD advisor Olivia Caramello. 

Having reached this point, the Morita equivalence problem breaks down into two parts. First,

> Which $X$s give equivalent $D(X)$s *and identical markings*?

In the ring case, this reduces to isomorphism: as soon as we know which module is the ring acting on itself, we know the ring up to isomorphism. In the topological group case, two groups give the same marking (surjective point) if and only if they have the same completion. If a given equivalence problem is like the topological group case in the sense that the $X$ recovered from a marking is a 'completion' of the $X$ generating that marking, then we can extract a condition for two $X$s to be equivalent in this sense by the existence of a suitable cospan between them.

The complementary question is:

> How do equivalences of $A$s transform markings?

Informally, this is better understood as the way in which one presentation for $A$ as a $D(X)$ 'sees' another. In the ring case, this is where the bimodules come from: an equivalence between $R$-Mod and $S$-Mod sends the 'marked' module $R$ to some left $S$-module, equipped with a right $R$-action by functoriality, and Morita's theorem amounts to characterising what that $(S,R)$-bimodule "looks like". In the topological group case, things are more complicated: a priori, there is no reason for the category of points to be connected (for the points to be able to "see" one another). I might come back to that example in another post.

## Monoids

I took this route in order to examine Morita equivalence for discrete monoids acting on sets [last year](https://arxiv.org/abs/1905.10277). I was able to take advantage of the more general Morita equivalence result that two presheaf toposes on small categories $\mathcal{C}$ and $\mathcal{D}$ are equivalent if and only if they have equivalent idempotent-completion, and further that essential geometric morphisms between toposes (and in particular equivalences) correspond bijectively to functors between these completions. This meant that for a suitable notion of morphism between monoids, namely semigroup homomorphisms, I was able to reflect this Morita equivalence to a notion of equivalence on the category of monoids. By treating bimodules as morphisms between rings, with the tensor product as composition, a similar result is achieved there.

I have since been working on the comparable problem for topological monoids, still acting on sets. Needless to say, this is a harder problem: I no longer have access to the techniques described in the last paragraph. But that only makes things more interesting! Analogously to the topological group problem discussed above, if we separate the Morita equivalence problem into two pieces, the first part (of identifying how monoids can be reconstructed from markings) turns out to be manageable. The full Morita equivalence problem is more challenging.

In the absence of an elementary characterisation of Morita equivalence, the next best thing is to *bound the equivalence*. What do I mean by that? The categories involved are huge: Grothendieck toposes have proper classes of objects! However, a topos generated in a particular way has its structure determined by a set of objects. If we can choose a set of generating objects whose members are characterised in a categorical way, this class will be invariant under equivalence, and so Morita equivalence is reduced to equivalence of these manageable subcategories. For topological monoids, I have arrived at the following:

**Theorem**: Two topological monoids are Morita equivalent (have equivalent categories of actions on discrete spaces) if and only if they have equivalent categories of cyclic actions (actions generated by a single element).

I won't prove it here (it may appear in some joint work with Jens Hemelaer before the topological monoid paper is finalised), but it isn't too hard once you're looking for it.

## Conclusion

Morita equivalence problems, in the sense I describe here, are an important piece of understanding how various constructions in mathematics transform information. I hope that this post illuminates the shape of this problem, some possible obstacles, and a general strategy, if not for solving the problem in full, at least for thinking about it and tackling a more manageable sub-problem.

comment_issue_id: 2
