# Problem 2 – How Many Pairwise Negative Dot Products?

## Problem

(Informal paraphrase of Strang’s challenge)

1. **In the plane** (say the \(yz\)-plane, but effectively \(\mathbb{R}^2\)):  
   Can three vectors \(u, v, w\) all have pairwise _negative_ dot products? That is, is it possible that
   \[
   u \cdot v < 0, \quad v \cdot w < 0, \quad u \cdot w < 0
   \]
   for three vectors in the plane?

2. **In three-dimensional space** \(\mathbb{R}^3\):  
   How many vectors can you have such that **every pair** has a negative dot product?

   Strang notes:

   > “Four of those vectors in the plane would certainly be impossible…”

   We want to understand what is possible in the plane, and get some intuition for 3D.

---

## Solution

### 1. Three vectors in the plane with all pairwise negative dot products

We work in \(\mathbb{R}^2\).  
A dot product is negative when the angle between the two vectors is **greater than \(90^\circ\)** and less than \(270^\circ\).

So we are looking for three vectors whose directions (angles) are such that **every pair forms an angle strictly between \(90^\circ\) and \(270^\circ\)**.

Let the directions of \(u, v, w\) (in radians or degrees) be \(\alpha, \beta, \gamma\) on the unit circle. Then:

- \(u\cdot v < 0 \iff\) angle between \(\alpha\) and \(\beta\) is in \((90^\circ, 270^\circ)\),
- similarly for \((v, w)\) and \((u, w)\).

#### Construction (explicit example)

Take three unit vectors at angles:
\[
\alpha = 0^\circ,\quad \beta = 140^\circ,\quad \gamma = 260^\circ.
\]

Now check pairwise angles:

- Between \(\alpha=0^\circ\) and \(\beta=140^\circ\):  
  angle \(= 140^\circ \in (90^\circ, 270^\circ)\) → dot product negative.
- Between \(\alpha=0^\circ\) and \(\gamma=260^\circ\):  
  the smaller angle is \(360^\circ - 260^\circ = 100^\circ \in (90^\circ, 270^\circ)\) → dot product negative.
- Between \(\beta=140^\circ\) and \(\gamma=260^\circ\):  
  angle \(= 260 - 140 = 120^\circ \in (90^\circ, 270^\circ)\) → dot product negative.

So all three pairs have negative dot product.

Therefore:
\[
\boxed{\text{Yes, in the plane it is possible to have 3 vectors with all pairwise negative dot products.}}
\]

We have even given an explicit construction.

---

### 2. Why 4 such vectors in the plane are impossible

Now suppose we try to have **four** nonzero vectors in \(\mathbb{R}^2\), say \(v_1, v_2, v_3, v_4\), such that

\[
v_i \cdot v_j < 0 \quad \text{for all } i \neq j.
\]

This means: the angle between _every_ pair of vectors is strictly between \(90^\circ\) and \(270^\circ\).

Think in terms of directions (angles on the unit circle). Represent each vector by a point on the circle.

Key geometric fact in \(\mathbb{R}^2\):

> If all pairwise angles between vectors lie in \((90^\circ, 270^\circ)\), then **all** directions must lie inside some open semicircle (an arc of length \(< 180^\circ\)). But if they all lie in some semicircle, there will always be two that form an angle \(\le 90^\circ\) (so their dot product is nonnegative).

Let’s make this precise with an argument:

#### Argument by ordering angles

Let the angles of the four vectors be:
\[
0^\circ \le \theta_1 < \theta_2 < \theta_3 < \theta_4 < 360^\circ.
\]

If any two differ by more than \(180^\circ\), we can always choose the **supplementary angle** (because the angle between lines is taken as the smaller one), but if the spread is too large we will run into trouble.

For all pairwise angles to be \(> 90^\circ\), we need that each vector is more than \(90^\circ\) away from every other.

Consider the smallest and largest angles, \(\theta_1\) and \(\theta_4\).  
The angle between these directions, going the shorter way around the circle, is:
\[
\min(\theta_4 - \theta_1,\ 360^\circ - (\theta_4 - \theta_1)).
\]

For their dot product to be negative, this minimum must exceed \(90^\circ\).

Now look at the “span” \(\theta_4 - \theta_1\):

- If \(\theta_4 - \theta_1 \le 180^\circ\):  
  The shorter angle between them is \(\theta_4 - \theta_1\).  
  So we need \(\theta_4 - \theta_1 > 90^\circ\).

- If \(\theta_4 - \theta_1 > 180^\circ\):  
  The shorter angle is \(360^\circ - (\theta_4 - \theta_1) < 180^\circ\).  
  For it to be > \(90^\circ\), we require:
  \[
  360^\circ - (\theta_4 - \theta_1) > 90^\circ \iff \theta_4 - \theta_1 < 270^\circ.
  \]

So \(\theta_4 - \theta_1\) must be in the range \((90^\circ, 270^\circ)\).

The circle is only \(360^\circ\) wide. Packing four angles so that every pair differs (in circular angle) by more than \(90^\circ\) is impossible: the total “minimum separation” needed for four points would be strictly greater than \(4 \cdot 90^\circ = 360^\circ\), which overflows the circle.

More intuitive version:

- Put the four angle points on the circle.
- Around each point, draw an open arc of \(90^\circ\) on each side that is **forbidden** for any other point (otherwise some pair would be \(\le 90^\circ\) apart).
- Each point “claims” at least an open arc of length \(180^\circ\) where no other direction may lie.
- Four such disjoint arcs cannot fit into a circle of \(360^\circ\).

Hence:

\[
\boxed{\text{In the plane, you cannot have 4 vectors all with pairwise negative dot products. The maximum is 3.}}
\]

This matches Strang’s comment: “Four of those vectors in the plane would certainly be impossible…”

---

### 3. What about \(\mathbb{R}^3\)?

In \(\mathbb{R}^3\), the situation is richer. Directions correspond to points on the **unit sphere** \(S^2\) instead of the unit circle.

The condition “dot product < 0” means the angle between any two vectors is \(> 90^\circ\). Geometrically:

- For each direction on the sphere, the set of directions making a non-positive dot product is a **closed hemisphere**.
- We want a set of unit vectors such that **no pair** is in the same closed hemisphere with angle \(\le 90^\circ\); equivalently, every pair lies outside each other’s “acute cone”.

One famous configuration in \(\mathbb{R}^3\):

- Take the vertices of a **regular tetrahedron** centered at the origin.
- The angle between any two radius vectors is greater than \(90^\circ\)? Actually, for a regular tetrahedron, the angle between any two vertices (as vectors from the center) has a constant cosine of \(-\frac{1}{3}\), so the angle is:
  \[
  \arccos\left(-\frac{1}{3}\right) \approx 109.47^\circ > 90^\circ.
  \]
- Therefore, the four vertex vectors from the center of a regular tetrahedron give **four vectors in \(\mathbb{R}^3\) whose pairwise dot products are all negative**.

So in \(\mathbb{R}^3\):

\[
\boxed{\text{At least 4 vectors with all pairwise dot products negative exist (tetrahedron vertices).}}
\]

Strang says: “I don’t know how many vectors in \( \mathbb{R}^3 \) space can have all negative dot products.”  
This is a deeper geometric/combinatorial question related to **sphere packings and acute/obtuse sets** on the sphere. The regular tetrahedron gives a clean example of 4; more may be possible, but the maximal number is nontrivial to determine.

---

## Geometric Insight

- In **2D**, the unit circle is too “small” to host four directions all more than \(90^\circ\) apart. Three vectors can be placed so that each pair forms an obtuse angle; a fourth inevitably creates at least one acute or right angle.
- In **3D**, the extra dimension allows directions to “spread out” more. The regular tetrahedron is a beautiful symmetric configuration where each pair of vectors is obtuse.

This ties linear algebra (dot products, angles, norms) with **spherical geometry** and **combinatorics of angles**.

---

## Generalization / Comments

- In \(\mathbb{R}^2\), the maximum size of a set with all pairwise negative dot products is \(3\).
- In \(\mathbb{R}^3\), the set of tetrahedron vertices shows the maximum is at least \(4\).
- More generally, questions of the form _“What is the largest set of vectors such that all pairwise angles are obtuse?”_ are related to **equiangular line sets** and **spherical codes**, deep topics in geometry and coding theory.
