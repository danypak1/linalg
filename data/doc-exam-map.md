# Index and exam map

Five cheat sheets, organised by **task type** — the kinds of problem that actually appear on the papers — rather than by textbook chapter. Every card follows the same pattern: how to recognise the task → the algorithm → the formula → a mini worked example → where students lose points.

This index is free. The cards themselves come with the course.

**Numbering on this page.** A reference of the form §X.Y always means section Y of module X of this course — the section the link opens. The lesson slides the course was built from, and the homework sheets, are numbered separately; they are written out in full, as "Lesson 5.3" and "HW 5-1", and never behind a §.

**Sources cross-checked to build this map:** the Model Test for the mid-term, the Linear Algebra Midterm 2024, the Linear Algebra Final Exam 2024, and all eighteen homework assignments, HW 1-1 through HW 5-1.

---

## Which exam problem → which card

### Model Test for the mid-term

| # | Problem | Card |
|---|---|---|
| 1(1) | Multiply a chain of three matrices | [02] Card 2.1 |
| 1(2) | Compute $f(A) = A^3+A^2+A+I$ | [05] Card 5.3 |
| 2(1) | Row reduce to echelon form, find the rank | [04] Card 4.1 |
| 2(2) | Find the inverse of a $3\times3$ matrix | [02] Card 2.4 |
| 3(1) | Solve a homogeneous system $A\mathbf{x}=\mathbf{0}$ | [04] Card 4.2 |
| 3(2) | Solve a non-homogeneous system $A\mathbf{x}=\mathbf{b}$ | [04] Card 4.3 |
| 4 | Maximal linearly independent subset of a set of vectors | [04] Card 4.5 |

### Linear Algebra Midterm 2024

| # | Problem | Card |
|---|---|---|
| I.1 | Multiply $AB$ | [02] Card 2.1 |
| I.2 | "Switching the rows and columns of $B$" gives $C=B^{T}$; compute $CAB$ | [02] Cards 2.1 + 2.6 |
| II | Plane $c\mathbf{v}+d\mathbf{w}$: write the general point, check $\mathbf{0}$ lies on it, verify the normal, the unit vector, the plane equation | **[01] Cards 1.2, 1.3** |
| III.1 | $A\mathbf{x}=\mathbf{b}$ → elimination to $U\mathbf{x}=\mathbf{c}$ → back substitution | [02] Card 2.2 |
| III.2 | Find $A^{-1}$ | [02] Card 2.4 |
| III.3 | Recover $L$ from the $U$ you found, i.e. $A=LU$ | [02] Card 2.5 |

### Linear Algebra Final Exam 2024

| # | Problem | Card |
|---|---|---|
| I.1 | **Prove:** if $\mathbf{x}$ is an eigenvector of $A$, then $\mathbf{x}$ is an eigenvector of $A^2$ | [05] Card 5.4 |
| I.2 | Find the eigenvalues and eigenvectors of a $2\times2$ matrix | [05] Cards 5.1, 5.2 |
| II.1 | Find $\det(A)$, $3\times3$ | [03] Card 3.2 |
| II.2 | $AC^{T} = \det(A)\,I$; find $\det(C)$ | [03] Card 3.4 |
| III.1 | Use row reduction to find $c$ making $A\mathbf{x}=\mathbf{b}$ consistent | [04] Card 4.1 |
| III.2 | Determine the free variables for $A\mathbf{x}=\mathbf{0}$ | [04] Card 4.2 |
| IV | Multiply $3\times3$ matrices | [02] Card 2.1 |

**Note.** Final I.1 is the only place in any of these papers that asks you to *write* a proof. Everything else is computational — but nine homework items need a proof **technique** rather than a computation, and those are flagged on the cards that cover them.

---

## The cards

| Card set | Covers | Module |
|---|---|---|
| [**[01] Vectors and dot products**](#/docs/ch1-vectors) | combinations, length, dot product, angles, perpendicularity, planes, $A\mathbf{x}$ | [Module 01](#/ch01/learn) |
| [**[02] Matrices, elimination, inverse, LU**](#/docs/ch2-matrices) | the two pictures, elimination and pivots, matrix multiplication, inverses, $A=LU$, transposes and permutations | [Module 02](#/ch02/learn) |
| [**[03] Determinants**](#/docs/ch3-determinants) | the three defining properties, determinant by elimination, cofactors, the adjugate identity, Cramer's rule, area and volume | [Module 03](#/ch03/learn) |
| [**[04] Vector spaces, rank, systems**](#/docs/ch4-spaces) | subspaces, nullspace and RREF, rank and free variables, the complete solution, independence, basis and dimension | [Module 04](#/ch04/learn) |
| [**[05] Eigenvalues and eigenvectors**](#/docs/ch5-eigen) | the characteristic equation, eigenvectors and eigenspaces, the trace/determinant check, powers of $A$, $AB$ against $BA$ | [Module 05](#/ch05/learn) |

Card [05] covers all of Lesson 5.1 **through Lesson 5.3** of the original course. Some older contents pages stop at Lesson 5.2; Lesson 5.3 is where the one examinable proof lives (Final I.1, worked in [§5.10](#/ch05/learn)) and where $AB$ and $BA$ are shown to share eigenvalues (HW 5-1(2), worked in [§5.12](#/ch05/learn)), so it is not optional.

**One correction to this map, found while the modules were written.** It sends Model Test 1(2) — compute $f(A)=A^3+A^2+A+I$ — to Card 5.3, the diagonalisation shortcut. That matrix has trace $2$ and determinant $4$, so its characteristic polynomial has discriminant $-12$: **no real eigenvalues, nothing to diagonalise**. Card 5.3 now carries the direct computation instead, and [§5.11](#/ch05/learn) works it through. Answering that question by diagonalising cannot be made to work, however carefully it is done.

---

## The five mistakes that actually cost points

Collected from the course notes — worth re-reading before any paper.

1. **Order of elimination steps** — forgetting which row is subtracted from which, or in what order.
2. **Sign of the determinant** — forgetting that swapping two rows flips the sign of $\det$.
3. **Order of matrix multiplication** — $AB \ne BA$, and $(AB)^{T} = B^{T}A^{T}$: the order reverses.
4. **Basis vs span** — confusing "independent vectors that span the space" with "some vectors that happen to span it".
5. **Eigenvalue arithmetic** — slips expanding $\det(A-\lambda I)=0$, or a missed root of the characteristic polynomial.

---

> *Independent study guide for a first course in Linear Algebra. Every worked example and every practice question is written for this course. Where a problem from a past paper or a homework sheet is worked through, it is named where it appears — those papers are the student's own course materials, and they are quoted to show how the method applies to them, never passed off as this course's own. Not affiliated with or endorsed by any university or instructor, and not endorsed by Strang's Introduction to Linear Algebra, which it follows as a reference.*
