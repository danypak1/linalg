# Module 01 — Summary

Everything examinable from Vectors, Length and Matrices, on one page.

## The objects

| Object | Definition | Picture |
|---|---|---|
| Vector $\mathbf{v}\in\mathbb{R}^n$ | ordered column of $n$ real numbers | arrow from the origin to the point |
| $\mathbf{v}+\mathbf{w}$ | add matching components | tip-to-tail; the parallelogram diagonal |
| $c\mathbf{v}$ | multiply every component by $c$ | stretch ($c>1$), shrink ($0<c<1$), reverse ($c<0$) — never off $\mathbf{v}$'s line |
| $c_1\mathbf{v}_1+\cdots+c_k\mathbf{v}_k$ | linear combination | the central object of the whole course |
| $\|\mathbf{v}\|$ | $\sqrt{v_1^2+\cdots+v_n^2}$ | length of the arrow |
| $\mathbf{v}\cdot\mathbf{w}$ | $v_1w_1+\cdots+v_nw_n$ — a **scalar** | how aligned the two are |
| Matrix $A$ ($m\times n$) | $m$ rows, $n$ columns; $a_{ij}$ = row $i$, column $j$ | $n$ column vectors standing side by side |
| $A\mathbf{x}$ | $x_1\mathbf{a}_1+\cdots+x_n\mathbf{a}_n$ | the columns of $A$, mixed by the recipe $\mathbf{x}$ |

## The formulas

| Formula | What it does | Use it when |
|---|---|---|
| $\mathbf{v}+\mathbf{w}$, $c\mathbf{v}$ component-wise | combine or scale moves | always; sizes must match to add |
| $\|\mathbf{v}\| = \sqrt{\mathbf{v}\cdot\mathbf{v}}$ | length from the dot product | converting between the two |
| $\mathbf{v}\cdot\mathbf{w} = \|\mathbf{v}\|\|\mathbf{w}\|\cos\theta$ | ties arithmetic to geometry | any angle question (Theorem 1) |
| $\cos\theta = \dfrac{\mathbf{v}\cdot\mathbf{w}}{\|\mathbf{v}\|\|\mathbf{w}\|}$ | the angle itself | computing $\theta$ from components; a negative value is an obtuse angle, so the sign is carried to the end |
| $\mathbf{v}\cdot\mathbf{w}=0 \iff \mathbf{v}\perp\mathbf{w}$ | right-angle test | verifying perpendicularity (Corollary 1) |
| $\mathbf{v}\perp\mathbf{w} \Rightarrow \|\mathbf{v}+\mathbf{w}\|^2 = \|\mathbf{v}\|^2+\|\mathbf{w}\|^2$ | Pythagoras, vector form | rectangle checks (Corollary 2) |
| $\|\mathbf{v}+\mathbf{w}\|^2+\|\mathbf{v}-\mathbf{w}\|^2 = 2\|\mathbf{v}\|^2+2\|\mathbf{w}\|^2$ | parallelogram law | relating diagonals to sides — holds for **every** pair |
| $\mathbf{u} = \dfrac{1}{\|\mathbf{v}\|}\mathbf{v}$ | unit vector | when only direction matters |
| $\|c\mathbf{v}\| = |c|\,\|\mathbf{v}\|$ | scaling a length | inside normalising proofs |
| $\mathbf{n}\cdot\mathbf{x}=0$ | plane through the origin with normal $\mathbf{n}$ | writing a plane's equation |
| $v_1w_2-v_2w_1 = 0$ | parallel test in $\mathbb{R}^2$ | before assuming $c\mathbf{v}+d\mathbf{w}=\mathbf{b}$ is solvable |
| $(A\mathbf{x})_i = a_{i1}x_1+\cdots+a_{in}x_n$ | row computation | fastest way to compute by hand (Theorem 2) |
| $A^{-1}(A\mathbf{x}) = \mathbf{x}$ | informal inverse | when the undo pattern is readable directly |

## The results, and how much proof each one needs

| Result | Statement | Proof status |
|---|---|---|
| Fact 1 | Two non-parallel vectors in $\mathbb{R}^2$ reach every point, uniquely; two parallel ones reach one line | three-line justification; know the *reason*, not a formal proof |
| Lemma 1 | dot product is symmetric, distributive, pulls out scalars, and $\mathbf{v}\cdot\mathbf{v}\ge0$ | short proof, one component at a time — the expansion technique matters more than the statement |
| **Theorem 1** | $\mathbf{v}\cdot\mathbf{w} = \|\mathbf{v}\|\|\mathbf{w}\|\cos\theta$ | **know the proof**: Law of Cosines vs expanding $(\mathbf{v}-\mathbf{w})\cdot(\mathbf{v}-\mathbf{w})$, then equate |
| Corollary 1 | $\mathbf{v}\cdot\mathbf{w}=0 \iff$ perpendicular | two lines from Theorem 1 |
| Corollary 2 | Pythagoras in vector form | same expansion with $+$; the middle term dies |
| parallelogram law | holds for all $\mathbf{v},\mathbf{w}$ | both expansions added; nothing is assumed about angles |
| unit vector | $\mathbf{v}/\|\mathbf{v}\|$ has length 1 | one line, via $\|c\mathbf{v}\|=|c|\|\mathbf{v}\|$ |
| Fact 2 | $\mathbf{n}\cdot\mathbf{x}=0$ is a plane; two dot-product checks cover all of it | the two-check argument is the examinable part |
| Theorem 2 | rows and columns give the same $A\mathbf{x}$ | know what it says and use it as a check; the derivation is collapsible in the notes |
| Fact 3 | $A^{-1}$ undoes $A$, so $\mathbf{x}=A^{-1}\mathbf{b}$ | informal here; Module 02 makes it precise |

## Method: solving $c\mathbf{v}+d\mathbf{w}=\mathbf{b}$

1. **Test first.** $v_1w_2-v_2w_1 = 0$? Then the combinations only reach one line — check whether $\mathbf{b}$ is on it before solving.
2. **Expand** the left side component by component.
3. **Match components** — one vector equation becomes several scalar equations.
4. **Solve** by elimination or substitution.
5. **Check** by substituting back. With more equations than unknowns (e.g. two vectors in $\mathbb{R}^3$), the unused equations are genuine consistency tests, and the target may fail them.

## Method: computing $A\mathbf{x}$

- **By columns** (the definition): scale each column of $A$ by the matching entry of $\mathbf{x}$, add.
- **By rows** (Theorem 2): dot row $i$ of $A$ with $\mathbf{x}$ to get output entry $i$.
- Legal only if columns of $A$ = components of $\mathbf{x}$. Output has as many components as $A$ has **rows**.
- Do one, check with the other. Every time.

## Where this module is examined

| Task | Where it appeared |
|---|---|
| Plane $c\mathbf{v}+d\mathbf{w}$: components, checking $\mathbf{0}$ lies on it, finding the normal and unit vector, writing the plane equation | Midterm 2024, Problem II — all four parts |
| Computing $A\mathbf{x}$ by rows and by columns, on the same product | HW 2-1 |
| Unit vectors, angles from cosines (including an obtuse one), constructing a perpendicular unit vector in $\mathbb{R}^2$ and in $\mathbb{R}^3$, proving a parallelogram is a rectangle, the parallelogram law | HW 1-2 |
| Linear combinations, solving $c\mathbf{v}+d\mathbf{w}=\mathbf{b}$ | HW 1-1 |
| Building $\mathbf{b}$ as $S\mathbf{x}$, the difference equation and its inverse | HW 1-3 |

## The eight sentences most likely to be needed on an exam

1. A linear combination scales each vector and adds the results — nothing else.
2. Two vectors in the plane reach every point unless one is a multiple of the other, in which case they reach one line.
3. Two vectors are equal exactly when every component matches, which is what turns a vector equation into scalar equations.
4. $\|\mathbf{v}\| = \sqrt{\mathbf{v}\cdot\mathbf{v}}$.
5. $\mathbf{v}\cdot\mathbf{w} = \|\mathbf{v}\|\|\mathbf{w}\|\cos\theta$, proved by computing $\|\mathbf{v}-\mathbf{w}\|^2$ twice — once by the Law of Cosines, once by expanding the dot product.
6. $\mathbf{v}\cdot\mathbf{w}=0$ means perpendicular; it does **not** mean either vector is zero. A negative dot product means an obtuse angle — e.g. $(2,1)\cdot(-1,-3) = -5$ gives $\cos\theta = -1/\sqrt2$ and $\theta = 135°$.
7. Checking $\mathbf{n}\cdot\mathbf{v}=0$ and $\mathbf{n}\cdot\mathbf{w}=0$ proves $\mathbf{n}$ is perpendicular to every point of the plane they span, because $\mathbf{n}\cdot(c\mathbf{v}+d\mathbf{w}) = c(\mathbf{n}\cdot\mathbf{v})+d(\mathbf{n}\cdot\mathbf{w}) = 0$.
8. $A\mathbf{x}$ is a combination of the columns of $A$; computing it row by row gives the same vector, which is a free check on your arithmetic.

---

> *Independent study guide for a first course in Linear Algebra. Every worked example and every practice question is written for this course. Where a problem from a past paper or a homework sheet is worked through, it is named where it appears — those papers are the student's own course materials, and they are quoted to show how the method applies to them, never passed off as this course's own. Not affiliated with or endorsed by any university or instructor, and not endorsed by Strang's Introduction to Linear Algebra, which it follows as a reference.*
