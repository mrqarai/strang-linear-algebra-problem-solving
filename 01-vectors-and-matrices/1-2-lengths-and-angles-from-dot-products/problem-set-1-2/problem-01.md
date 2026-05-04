# Problem 1 – Extremal Values of ‖v − w‖ and v · w

## Problem

Given vectors \(v\) and \(w\) in \(\mathbb{R}^n\) with
\[
\|v\| = 5,\quad \|w\| = 3,
\]
find:

1. The **smallest** and **largest** possible values of the norm \(\|v - w\|\).
2. The **smallest** and **largest** possible values of the dot product \(v \cdot w\).

---

## Solution

### 1. Extremal values of \(\|v - w\|\)

We use the identity
\[
\|v - w\|^2 = \|v\|^2 + \|w\|^2 - 2\,v\cdot w.
\]

Let \(\theta\) be the angle between \(v\) and \(w\). Then
\[
v\cdot w = \|v\|\,\|w\|\cos\theta = 5 \cdot 3 \cos\theta = 15\cos\theta.
\]

Substitute into the formula:

\[
\|v - w\|^2 = 5^2 + 3^2 - 2(15\cos\theta)
= 25 + 9 - 30\cos\theta
= 34 - 30\cos\theta.
\]

Since \(-1 \le \cos\theta \le 1\), the expression
\[
34 - 30\cos\theta
\]
is minimized when \(\cos\theta\) is **maximal** (\(=1\)) and maximized when \(\cos\theta\) is **minimal** (\(=-1\)).

- When \(\cos\theta = 1\) (vectors parallel, same direction):
  \[
  \|v - w\|^2 = 34 - 30(1) = 4
  \quad\Rightarrow\quad
  \|v - w\| = 2.
  \]

- When \(\cos\theta = -1\) (vectors antiparallel, opposite directions):
  \[
  \|v - w\|^2 = 34 - 30(-1) = 64
  \quad\Rightarrow\quad
  \|v - w\| = 8.
  \]

Therefore:
\[
\boxed{
2 \le \|v - w\| \le 8
}
\]

---

### 2. Extremal values of \(v \cdot w\)

We already have:
\[
v\cdot w = 15\cos\theta,\quad \cos\theta \in [-1, 1].
\]

So:

- Maximum value (when \(\cos\theta = 1\)):
  \[
  v\cdot w\_{\max} = 15.
  \]
- Minimum value (when \(\cos\theta = -1\)):
  \[
  v\cdot w\_{\min} = -15.
  \]

Thus:
\[
\boxed{
-15 \le v\cdot w \le 15
}
\]

---

## Geometric Insight

- The possible values of \(\|v - w\|\) arise from the **law of cosines** on the triangle with sides \(\|v\|, \|w\|\), and \(\|v - w\|\).
- The **smallest** distance between the tips of \(v\) and \(w\) occurs when they are as aligned as possible (pointing in the same direction). Then the difference of their lengths is all that remains: \(5 - 3 = 2\).
- The **largest** distance occurs when they point in opposite directions. Then the “effective length” is \(5 + 3 = 8\).

So, in fact:
\[
\boxed{
|\|v\| - \|w\|| \le \|v - w\| \le \|v\| + \|w\|
}
\]
which is the triangle inequality and its reverse form.

For the dot product:

- Maximum \(= \|v\| \|w\|\) when they point in the same direction.
- Minimum \(= -\|v\| \|w\|\) when they point in opposite directions.

---

## Generalization / Comments

- This analysis works in any dimension \(n\); only the norms and angle matter.
- The bounds on \(\|v - w\|\) come from:
  \[
  \|v - w\|^2 = \|v\|^2 + \|w\|^2 - 2\|v\|\|w\|\cos\theta.
  \]
- The dot product bounds are a direct application of the **Cauchy–Schwarz inequality**:
  \[
  |v\cdot w| \le \|v\|\|w\|.
  \]
