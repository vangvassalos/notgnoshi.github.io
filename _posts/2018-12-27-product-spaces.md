---
layout: post
title: Product Spaces
meta: The difference between the box and product topologies in terms of their bases.
---

There is some preliminary information we need to cover before a discussion of product spaces makes sense.

## Topological Spaces

First, we must define a *topology* and a *topological space*.

A **topology** defined on a set $$X$$ is a collection $$\mathcal T$$ of subsets of $$X$$ that has the following properties:

1. $$\varnothing$$ and $$X$$ are contained in $$\mathcal T$$
2. Any arbitrary union of the elements of a subcollection of $$\mathcal T$$ is contained in $$\mathcal T$$
3. Any finite intersection of the elements of a finite subcollection of $$\mathcal T$$ is contained in $$\mathcal T$$

Then we say that $$X$$, along with a topology $$\mathcal T$$ defined on $$X$$ is called a **topological space**. Further, we say that if a subset $$U \subset X$$ is an element of $$\mathcal T$$, then $$U$$ is an **open set** of $$X$$.

### Example

Let $$X = \{a, b, c\}$$. Then there are many possible topologies that can be defined on $$X$$. Two such topologies are the collections

$$\mathcal T_1 = \big\{ \{\}, \{a, b\}, \{a, b, c\} \big\}$$

$$\mathcal T_2 = \big\{ \{\}, \{a\}, \{b, c\}, \{a, b, c\} \big\}$$

The empty set and the whole space are clearly contained in both topologies. Now take any subcollection of either topologies, say $$T_1 \subset \mathcal T_1 = \big\{ \{\}, \{a, b\} \big\}$$ or $$T_2 \subset \mathcal T_2 = \big\{ \{a\}, \{a, b, c\} \big\}$$. Note that $$\bigcup T_1 = \{a, b\}$$, which is contained in $$\mathcal T_1$$, and $$\bigcap T_1 = \{\}$$, which is also contained in $$\mathcal T_1$$. Similarly, note that $$\bigcup T_2 = \{a, b, c\}$$ is contained in $$\mathcal T_2$$, and $$\bigcap T_2 = \{a\}$$ is also contained in $$\mathcal T_2$$.

## Bases for Topological Spaces

Second, we must define what a *basis* for a topology is. Usually listing out every member of a topology $$\mathcal T$$ can get a bit... tiresome. So we define something easier to get our hands on, and build a topology from there.

If $$X$$ is a set, a **basis** for a topology on $$X$$ is a collection $$\mathcal B$$ of subsets of $$X$$ (called **basis elements**) such that

1. For each $$x \in X$$ there is at least one basis element $$B$$ containing $$x$$
2. If $$x$$ belongs to the intersection of two basis elements $$B_1$$ and $$B_2$$, then there exists a third basis element $$B_3$$ such that $$x \in B_3$$ and $$B_3 \subset B_1 \cap B_2$$

Then we define the **topology $$\mathcal T$$ generated by $$\mathcal B$$** as follows: A subset $$U \subset X$$ is said to be open in $$X$$ (that is, an element of $$\mathcal T$$) if for every $$x \in U$$, there exists of basis element $$B \in \mathcal B$$ such that $$x \in B$$ and $$B \subset U$$.

<img class="centered-real" src="{{ "/assets/posts/product-spaces/basis.svg" | prepend: site.baseurl }}" alt="basis-element-intersection">

If $$\mathcal B = \big\{ (a, b) \mid a < b \in \mathbb R \big\}$$ is the collection of all open intervals in $$\mathbb R$$, then the topology generated by $$\mathcal B$$ is called the **standard** or **usual** topology on $$\mathbb R$$.

## Cartesian Products

Third, we must discuss *cartesian products* in a more general sense than you might be familiar.

Let $$\mathcal A$$ be a nonempty collection of sets. An **indexing function** for $$\mathcal A$$ is a surjective function $$f:J \to \mathcal A$$. The set $$J$$ is called the **index set**. The collection $$\mathcal A$$, along with the function $$f$$, is called an **indexed family of sets**. For some $$\alpha \in J$$, we typically denote $$f(\alpha)$$ as $$A_\alpha$$, and denote the whole family of sets by $$\big\{A_\alpha\big\}_{\alpha \in J}$$.

Note that no restrictions are given on the index set $$J$$ or the collection $$\mathcal A$$! This means that both $$J$$ and $$\mathcal A$$ could be finite, countable, or even uncountable.

We will use this notation to redefine arbitrary unions, intersections, and products. Given some indexed family of sets $$\big\{A_\alpha\big\}_{\alpha \in J}$$, we define the arbitrary union of elements of $$\mathcal A$$ as

$$\bigcup_{\alpha \in J} A_\alpha = \big\{x \mid x \in A_\alpha \text{ for at least one } \alpha \in J \big\}$$

and the arbitrary intersection of elements of $$\mathcal A$$ as

$$\bigcap_{\alpha \in J} A_\alpha = \big\{x \mid x \in A_\alpha \text{ for every } \alpha \in J \big\}$$

We will define cartesian products of indexed families of sets in stages.

### Finite Products

Let $$m \in \mathbb Z_+$$. Given a set $$X$$, we define an **$$m$$-tuple** of elements of $$X$$ to be a function

$$\vec x : \{1, \dots, m\} \to X$$

We typically denote $$\vec x(i)$$ as $$x_i$$, and often denote the entire function $$\vec x$$ as

$$(x_1, \dots, x_m)$$

Now let $$\big\{A_1, \dots, A_m\big\}$$ be a *finite* family of sets indexed by the set $$\{1, \dots, m\}$$, and let $$X = A_1 \cup \cdots \cup A_m$$. We define the *finite* **cartesian product** of this family of sets, denoted by

$$\prod_{i = 1}^m A_i$$

or equivalently

$$A_1 \times \cdots \times A_m$$

as the collection of all $$m$$-tuples of elements of $$X$$, such that $$x_i \in A_i$$ for every $$i$$.

### Countable Products

Given a set $$X$$, we define an **$$\omega$$-tuple** of elements of $$X$$ to be a function

$$\vec x : \mathbb Z_+ \to X$$

We also call this function a **sequence** of elements of $$X$$, and typically denote it by the symbols

$$(x_1, x_2, \dots )$$

or

$$(x_n)_{n \in \mathbb Z_+}$$

Now let $$\big\{A_1, A_2, \dots\big\}$$ be a family of sets indexed by $$\mathbb Z_+$$, and let $$X = \bigcup_{i \in \mathbb Z_+} A_i$$. Then the *countable* **cartesian product** of this family of sets, denote by

$$\prod_{i \in \mathbb Z_+} A_i$$

or equivalently

$$A_1 \times A_2 \times \cdots$$

is defined as the set of all $$\omega$$-tuples of elements of $$X$$ such that $$x_i \in A_i$$ for every $$i \in \mathbb Z_+$$.

If each $$A_i = X$$, then the product $$\prod A_i$$ is denoted by $$X^\omega$$, which is the collection of *all* $$\omega$$-tuples of elements of $$X$$.

### Arbitrary Products

Let $$J$$ be any index set. Given a set $$X$$, we define a $$J$$-tuple of elements of $$X$$ to be a function $$\vec x : J \to X$$. If $$\alpha \in J$$, we typically denote $$\vec x(\alpha)$$ as $$x_\alpha$$, and we often denote the function itself by

$$\big(x_\alpha\big)_{\alpha \in J}$$

and we denote the set of all $$J$$-tuples of elements of $$X$$ by $$X^J$$.

Now let $$\big\{A_\alpha\big\}_{\alpha \in J}$$ be some indexed family of sets, and let $$X = \bigcup_{\alpha \in J} A_\alpha$$. Then the *arbitrary* **cartesian product** of this indexed family of sets, denoted by

$$\prod_{\alpha \in J} A_\alpha$$

is defined to be the collection of all $$J$$-tuples of elements of $$X$$ such that $$x_\alpha \in A_\alpha$$ for every $$\alpha \in J$$. That is, it is the set of all functions

$$\vec x : J \to \bigcup_{\alpha \in J} A_\alpha$$

such that $$x_\alpha \in A_\alpha$$ for each $$\alpha \in J$$.

If $$J$$ is understood, we often denote the product simply by $$\prod A_\alpha$$ and an element of the product as $$\big(a_\alpha\big)$$.

## Product Spaces

As with the cartesian product, we will build our understanding of the product space in pieces.

### The Product of Two Spaces

Let $$X$$ and $$Y$$ be topological spaces. The **product topology** on $$X \times Y$$ is the topology with basis $$\mathcal B = \big\{ U \times V \mid \text{$U$ open in $X$, and $V$ open in $Y$} \big\}$$. We call $$X \times Y$$ a **product space**.

Now what if $$X$$ and $$Y$$ are given in terms of their bases? If $$\mathcal B$$ is a basis for the topology of $$X$$, and $$\mathcal C$$ is a basis for the topology of $$Y$$, then

$$\mathcal D = \big\{ B \times C \mid B \in \mathcal B, C \in \mathcal C\big\}$$

is a basis for the topology of $$X \times Y$$.

Now define $$\pi_1 : X \times Y \to X$$ be defined by $$\pi_1(x, y) = x$$ and $$\pi_2 : X \times Y \to Y$$ be defined by $$\pi_2(x, y) = y$$. $$\pi_1$$ and $$\pi_2$$ are called **projections** of $$X \times Y$$ onto the first and second factors respectively. But then if $$U$$ is open in $$X$$, then the set $$\pi_1^{-1}(U)$$ is the set $$U \times Y$$. Similarly, if $$V$$ is open in $$Y$$, then $$\pi_2^{-1}(V)$$ is the set $$X \times V$$.

Note that $$U \times V = \pi_1^{-1}(U) \cap \pi_2^{-1}(V)$$.

#### Example

Let us denote the space $$X$$ and an open set $$U \subset X$$ as

<img class="centered-real" src="{{ "/assets/posts/product-spaces/space-x.svg" | prepend: site.baseurl }}" alt="space-x">

Then given an open set $$V \subset Y$$, we can draw $$X \times Y$$, and $$U \times V$$ as

<img class="centered-real" src="{{ "/assets/posts/product-spaces/x-times-y.svg" | prepend: site.baseurl }}" alt="x-times-y">

However, we will soon see that this fails to generalize to higher dimensions, say for an uncountable product space.

### The Product of Arbitrarily Many Spaces

Recall that for the product of two spaces discussed above, we defined that basis of the product space $$X \times Y$$ as the collection $$\big\{U \times V \big\}$$ where each $$U$$ and $$V$$ are basis elements of the bases for $$X$$ and $$Y$$ respectively. However, this was a bold-faced lie. For reasons beyond the scope of this discussion, extending this definition to arbitrarily many topological spaces really *sucks*.

#### Box Topology

Let $$\displaystyle\big\{X_\alpha\big\}_{\alpha \in J}$$ be an indexed family of topological spaces. We define a topology on the product space $$\displaystyle\prod_{\alpha \in J} X_\alpha$$ using the basis

$$\left\{\prod_{\alpha \in J}U_\alpha \mid U_\alpha \text{ open in } X_\alpha\right\}$$

This basis generates the **box topology** on $$\prod x_\alpha$$.

#### Product Topology

Let $$\displaystyle\big\{X_\alpha\big\}_{\alpha \in J}$$ be an indexed family of topological spaces. We define a topology on the product space $$\displaystyle\prod_{\alpha \in J} X_\alpha$$ using the basis

$$\left\{\prod_{\alpha \in J}U_\alpha\right\}$$

where each $$U_\alpha = X_\alpha$$ *except for finitely many values of $$\alpha$$*. This basis generates the **product topology** on $$\prod x_\alpha$$. Note that the box and product topologies are identical when the family of topological spaces $$\big\{A_i\big\}_{i=1}^n$$ is finite!

### Pictures that *do* Generalize

As we remarked earlier, the visualization of a cartesian product below does not generalize to higher dimensions.

<img class="centered-real" src="{{ "/assets/posts/product-spaces/x-times-y.svg" | prepend: site.baseurl }}" alt="x-times-y">

Let us now introduce a new visualization method. Let us begin by visualizing the ordered pairs $$(x_1, y_1)$$ and $$(x_2, y_2)$$ in $$X \times Y$$. We lay the spaces $$X$$ and $$Y$$ vertically, and visualize points in their product as a sequence of dots joining the two spaces.

<img class="centered-real" src="{{ "/assets/posts/product-spaces/point.svg" | prepend: site.baseurl }}" alt="visualizing-a-point">

Since $$X \times Y$$ is a product of finitely many spaces, the box topology and the product topology are one and the same. So a basis element of one is a basis element of the other. In particular, if $$U$$ and $$V$$ are basis elements of $$X$$ and $$Y$$ respectively, then $$U \times V$$ is a basis element in the product space. Well, what does $$U \times V$$ look like?

Recall from the definition of the cartesian product, that $$U \times V$$ is defined as the collection of all points of $$X \times Y$$ such that the first coordinate is an element of $$U$$ and the second an element of $$V$$.

<img class="centered-real" src="{{ "/assets/posts/product-spaces/xy-basis.svg" | prepend: site.baseurl }}" alt="xy-basis">

The point of laying each $$X_\alpha$$ space vertically is intended to provide intuition for higher dimensional product spaces, even to the point of uncountably many dimensions. However it does have some limitations.

<img class="centered-real" src="{{ "/assets/posts/product-spaces/higher-dimensional-product-space.svg" | prepend: site.baseurl }}" alt="higher-dimensional-product-space">

For example, drawing distinct lines, and indexing them with the positive integers makes the assumption that the spaces $$\big\{X_\alpha\big\}$$ are countable. It may make more sense to draw the product space as a plane, where each infinitely thin vertical slice is a particular $$X_\alpha$$. However, this too has a shortcoming. It assumes that there is some order on $$\big\{X_\alpha\big\}$$ -- that is, we can somehow claim that some $$X_\beta$$ should be drawn before $$X_\gamma$$.

However, with these (and possibly other) shortcomings, this kind of visualization does prove useful for building intuition regarding product spaces.

### An Example of the Difference Between the Box and Product Topologies

Let $$f : A \to \prod_{\alpha \in J} X_\alpha$$ be given by

$$f(a) = \big(f_\alpha(a) \big)_{\alpha \in J}$$

where $$f_\alpha : A \to X_\alpha$$ for each $$\alpha \in J$$. Suppose $$\prod X_\alpha$$ has the product topology. Then the function $$f$$ is continuous if and only if each function $$f_\alpha$$ is continuous.

This is not true if $$\prod X_\alpha$$ is given the box topology. To see why, consider $$\mathbb R^\omega$$, the countably infinite product of $$\mathbb R$$ with itself.

$$\mathbb R^\omega = \prod_{n \in \mathbb Z_+} \mathbb R$$

Now for the sheer hell of it, define a function $$f : \mathbb R \to \mathbb R^\omega$$ given by

$$f(t) = \big(f_0(t), f_1(t), f_2(t), \dots\big) = \big(t, t, t, \dots \big)$$

<img class="centered-real" src="{{ "/assets/posts/product-spaces/sequence.svg" | prepend: site.baseurl }}" alt="sequence">

Note that each of the coordinate functions $$f_n : \mathbb R \to \mathbb R$$ by $$f_n(t) = t$$ are continuous. Therefore, if $$\mathbb R^\omega$$ is given the product topology, $$f$$ is continuous by the preceding theorem. However, what happens if we give $$\mathbb R^\omega$$ to box topology?

Consider $$B = \big(-1, 1\big) \times \left(-\frac{1}{2}, \frac{1}{2}\right) \times \left(-\frac{1}{3}, \frac{1}{3}\right) \times \cdots$$.

<img class="centered-real" src="{{ "/assets/posts/product-spaces/basis-element.svg" | prepend: site.baseurl }}" alt="basis-element">

$$B$$ is a basis element of the box topology, and is thus open. However, $$f^{-1}(B)$$ is *not* open, so then $$f$$ cannot be continuous. To see this, suppose by way of contradiction that $$f^{-1}(B)$$ *was* open.

Note that $$\big(0, 0, 0, \dots \big) \in B$$, and thus $$0 \in f^{-1}(B)$$. Now since $$f^{-1}(B)$$ is open by assumption, for every point $$x$$ in $$f^{-1}(B)$$ there is some neighborhood $$U$$ of $$x$$ contained in $$f^{-1}(B)$$. Thus there is some open interval $$(-\delta, \delta)$$ around $$0$$ contained in $$f^{-1}(B)$$.

<img class="centered-real" src="{{ "/assets/posts/product-spaces/sequence-interval.svg" | prepend: site.baseurl }}" alt="sequence-interval">

However, this implies that $$f\big((-\delta, \delta)\big) \subset B$$, but this implies that $$f_n\big((-\delta, \delta)\big) = (-\delta, \delta) \subset \left(-\frac{1}{n}, \frac{1}{n}\right)$$ for every $$n$$, but this is absurd and a contradiction.

Therefore $$f^{-1}(B)$$ cannot be open, and therefore $$f$$ cannot be continuous.
